---
title: "컬렉션에서 Culture를 구분하지 않는 문자열 작업 수행 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ArrayList.Sort 메서드"
  - "CaseInsensitiveComparer 클래스, using"
  - "CaseInsensitiveHashCodeProvider 클래스, using"
  - "컬렉션[.NET Framework], 문화권 비구분 문자열 연산"
  - "CollectionsUtil.CreateCaseInsensitiveHashtable 메서드"
  - "문화권 매개 변수"
  - "문화권 비구분 문자열 연산, 컬렉션"
  - "SortedList 클래스, 문화권 비구분 문자열 연산"
ms.assetid: 5cdc9396-a64b-4615-a1cd-b605db4c5983
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# 컬렉션에서 Culture를 구분하지 않는 문자열 작업 수행
<xref:System.Collections> 네임스페이스에는 기본적으로 문화권별 동작을 제공하는 클래스와 멤버가 있습니다.  <xref:System.Collections.CaseInsensitiveComparer> 및 <xref:System.Collections.CaseInsensitiveHashCodeProvider> 클래스의 기본 생성자는 <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=fullName> 속성을 사용하여 새 인스턴스를 초기화합니다.  [CollectionsUtil.CreateCaseInsensitiveHashTable](frlrfSystemCollectionsSpecializedCollectionsUtilClassCreateCaseInsensitiveHashtableTopic) 메서드의 모든 오버로드는 기본적으로 `Thread.CurrentCulture` 속성을 사용하여 <xref:System.Collections.Hashtable> 클래스의 새 인스턴스를 만듭니다.  <xref:System.Collections.ArrayList.Sort%2A?displayProperty=fullName> 메서드의 오버로드는 기본적으로 `Thread.CurrentCulture`를 사용하여 문화권별 정렬을 수행합니다.  문자열이 키로 사용된 경우 <xref:System.Collections.SortedList>에서 정렬 및 조회를 수행할 때 `Thread.CurrentCulture`의 영향을 받을 수 있습니다.  이 단원에 제공된 권장 사용 방법에 따라 `Collections` 네임스페이스에 있는 이러한 클래스 및 메서드에서 문화권을 구분하지 않는 결과를 얻을 수 있습니다.  
  
 **참고** 비교 메서드에 <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>를 전달하면 문화권을 구분하지 않는 비교가 수행됩니다.  그러나 파일 경로, 레지스트리 키, 환경 변수 등에 대해 비언어적인 비교를 수행하지는 않습니다.  비교 결과를 기반으로 하는 보안 결정을 지원하지도 않습니다.  비언어적인 비교나 결과 기반의 보안 결정 지원의 경우 응용 프로그램에서 <xref:System.StringComparison> 값을 받아들이는 비교 메서드를 사용해야 합니다.  그런 다음 응용 프로그램이 <xref:System.StringComparison>을 전달해야 합니다.  
  
## CaseInsensitiveComparer 및 CaseInsensitiveHashCodeProvider 클래스 사용  
 `CaseInsensitiveHashCodeProvider` 및 `CaseInsensitiveComparer`의 기본 생성자는 `Thread.CurrentCulture`를 사용하여 클래스의 새 인스턴스를 초기화하므로 문화권을 구분하는 동작이 발생합니다.  다음 코드 예제에서는 `CaseInsensitiveHashCodeProvider` 및 `CaseInsensitiveComparer`의 기본 생성자를 사용하므로 문화권을 구분하는 `Hashtable`의 생성자를 보여 줍니다.  
  
```vb  
internalHashtable = New Hashtable(CaseInsensitiveHashCodeProvider.Default, CaseInsensitiveComparer.Default)  
  
```  
  
```csharp  
internalHashtable = new Hashtable(CaseInsensitiveHashCodeProvider.Default, CaseInsensitiveComparer.Default);  
```  
  
 `CaseInsensitiveComparer` 및 `CaseInsensitiveHashCodeProvider` 클래스를 사용하여 문화권을 구분하지 않는 `Hashtable`을 만들려면 `culture` 매개 변수를 받아들이는 생성자를 사용하여 이러한 클래스의 새 인스턴스를 초기화합니다.  `culture` 매개 변수에 <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>를 지정합니다.  다음 코드 예제에서는 문화권을 구분하지 않는 `Hashtable`의 생성자를 보여 줍니다.  
  
```vb  
internalHashtable = New Hashtable(New  
    CaseInsensitiveHashCodeProvider(CultureInfo.InvariantCulture),  
    New CaseInsensitiveComparer(CultureInfo.InvariantCulture))  
  
```  
  
```csharp  
internalHashtable = new Hashtable(new CaseInsensitiveHashCodeProvider  
    (CultureInfo.InvariantCulture),   
    new CaseInsensitiveComparer(CultureInfo.InvariantCulture));  
```  
  
## CollectionsUtil.CreateCaseInsensitiveHashTable 메서드 사용  
 `CollectionsUtil.CreateCaseInsensitiveHashTable` 메서드는 문자열의 대\/소문자를 무시하는 `Hashtable` 클래스의 새 인스턴스를 만드는 데 유용한 바로 가기입니다.  그러나 `CollectionsUtil.CreateCaseInsensitiveHashTable` 메서드의 모든 오버로드는 `Thread.CurrentCulture` 속성을 사용하기 때문에 문화권을 구분합니다.  이 메서드를 사용하여 문화권을 구분하지 않는 `Hashtable`을 만들 수는 없습니다.  문화권을 구분하지 않는 `Hashtable`을 만들려면 `culture` 매개 변수를 받아들이는 `Hashtable` 생성자를 사용합니다.  `culture` 매개 변수에 `CultureInfo.InvariantCulture`를 지정합니다.  다음 코드 예제에서는 문화권을 구분하지 않는 `Hashtable`의 생성자를 보여 줍니다.  
  
```vb  
internalHashtable = New Hashtable(New  
    CaseInsensitiveHashCodeProvider(CultureInfo.InvariantCulture),  
    New CaseInsensitiveComparer(CultureInfo.InvariantCulture))  
  
```  
  
```csharp  
internalHashtable = new Hashtable(new CaseInsensitiveHashCodeProvider  
    (CultureInfo.InvariantCulture),   
    new CaseInsensitiveComparer(CultureInfo.InvariantCulture));  
```  
  
<a name="cpconperformingculture-insensitivestringoperationsincollectionsanchor1"></a>   
## SortedList 클래스 사용  
 `SortedList`는 키별로 정렬되며 키 및 인덱스로 액세스할 수 있는 키\-값 쌍의 컬렉션을 나타냅니다.  문자열이 키인 `SortedList`를 사용하는 경우 정렬 및 조회가 `Thread.CurrentCulture` 속성의 영향을 받을 수 있습니다.  `SortedList`에서 문화권을 구분하지 않는 동작을 얻으려면 `comparer` 매개 변수를 받아들이는 생성자 중 하나를 사용하여 `SortedList`를 만듭니다.  `comparer` 매개 변수는 키를 비교할 때 사용할 <xref:System.Collections.IComparer> 구현을 지정합니다.  `CultureInfo.InvariantCulture`를 사용하여 키를 비교하는 사용자 지정 비교자 클래스를 매개 변수에 지정합니다.  다음 예제에서는 `SortedList` 생성자에 대한 `comparer` 매개 변수로 지정할 수 있는, 문화권을 구분하지 않는 사용자 지정 비교자 클래스를 보여 줍니다.  
  
```vb  
Imports System  
Imports System.Collections  
Imports System.Globalization  
  
Friend Class InvariantComparer  
    Implements IComparer   
    Private m_compareInfo As CompareInfo  
    Friend Shared [Default] As New InvariantComparer()  
  
    Friend Sub New()  
        m_compareInfo = CultureInfo.InvariantCulture.CompareInfo  
    End Sub     
  
    Public Function Compare(a As Object, b As Object) As Integer _  
            Implements IComparer.Compare  
        Dim sa As String = CType(a, String)  
        Dim sb As String = CType(b, String)  
        If Not (sa Is Nothing) And Not (sb Is Nothing) Then  
            Return m_compareInfo.Compare(sa, sb)  
        Else  
            Return Comparer.Default.Compare(a, b)  
        End If  
    End Function  
End Class  
  
```  
  
```csharp  
using System;  
using System.Collections;  
using System.Globalization;  
  
internal class InvariantComparer : IComparer   
{  
    private CompareInfo m_compareInfo;  
    internal static readonly InvariantComparer Default = new  
        InvariantComparer();  
  
    internal InvariantComparer()   
    {  
        m_compareInfo = CultureInfo.InvariantCulture.CompareInfo;  
    }  
  
    public int Compare(Object a, Object b)  
    {  
        String sa = a as String;  
        String sb = b as String;  
        if (sa != null && sb != null)  
            return m_compareInfo.Compare(sa, sb);  
        else  
            return Comparer.Default.Compare(a,b);  
    }  
}  
```  
  
 일반적으로 사용자 지정 고정 비교자를 지정하지 않고 문자열에 `SortedList`를 사용할 경우 목록이 채워진 후에 `Thread.CurrentCulture`를 변경하면 목록이 무효가 될 수 있습니다.  
  
## ArrayList.Sort 메서드 사용  
 `ArrayList.Sort` 메서드의 오버로드는 기본적으로 `Thread.CurrentCulture` 속성을 사용하여 문화권을 구분하는 정렬을 수행합니다.  정렬 순서가 다르기 때문에 문화권마다 결과가 다를 수 있습니다.  문화권을 구분하는 동작을 제거하려면 `IComparer` 구현을 받아들이는 이 메서드의 오버로드를 사용합니다.  `CultureInfo.InvariantCulture`를 사용하는 사용자 지정 고정 비교자 클래스를 `comparer` 매개 변수에 지정합니다.  사용자 지정 고정 비교자 클래스의 예제는 [SortedList 클래스 사용](#cpconperformingculture-insensitivestringoperationsincollectionsanchor1) 항목에 있습니다.  
  
## 참고 항목  
 <xref:System.Collections.CaseInsensitiveComparer>   
 <xref:System.Collections.CaseInsensitiveHashCodeProvider>   
 <xref:System.Collections.ArrayList.Sort%2A?displayProperty=fullName>   
 <xref:System.Collections.SortedList>   
 <xref:System.Collections.Hashtable>   
 <xref:System.Collections.IComparer>   
 [Culture의 영향을 받지 않는 문자열 작업 수행](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)   
 [CollectionsUtil.CreateCaseInsensitiveHashTable 메서드](frlrfSystemCollectionsSpecializedCollectionsUtilClassCreateCaseInsensitiveHashtableTopic)