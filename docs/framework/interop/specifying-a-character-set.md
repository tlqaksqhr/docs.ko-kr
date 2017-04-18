---
title: "문자 집합 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "플랫폼 호출의 특성 필드, CharSet"
  - "CharSet 필드"
  - "플랫폼 호출, 특성 필드"
ms.assetid: a8347eb1-295f-46b9-8a78-63331f9ecc50
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# 문자 집합 지정
<xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=fullName> 필드는 문자열 마샬링을 제어하고 플랫폼 호출에서 DLL의 함수 이름을 찾는 방법을 결정합니다.  이 항목에서는 이들 두 동작에 대해 설명합니다.  
  
 일부 API에서는 문자열 인수를 사용하는 두 개의 함수 버전\(ANSI와 유니코드\)을 내보냅니다.  예를 들어 Win32 API에는 **MessageBox** 함수에 대해 다음과 같은 진입점 이름이 포함됩니다.  
  
-   **MessageBoxA**  
  
     1바이트 문자 ANSI 형식 지정을 제공하며, 진입점 이름은 뒤에 추가된 "A"로 구별됩니다.  **MessageBoxA** 호출은 항상 문자열을 ANSI 형식으로 마샬링하며, 이 방법은 Windows 95 및 Windows 98 플랫폼에 사용됩니다.  
  
-   **MessageBoxW**  
  
     2바이트 문자 유니코드 형식 지정을 제공하며, 진입점 이름은 뒤에 추가된 "W"로 구별됩니다.  **MessageBoxW** 호출은 항상 문자열을 유니코드 형식으로 마샬링하며, 이 방법은 Windows NT, Windows 2000 및 Windows XP 플랫폼에 사용됩니다.  
  
## 문자열 마샬링 및 이름 일치  
 **CharSet** 필드에는 다음 값을 사용할 수 있습니다.  
  
 **CharSet.Ansi**\(기본값\)  
  
-   문자열 마샬링  
  
     플랫폼 호출은 문자열을 관리되는 형식\(유니코드\)에서 ANSI 형식으로 마샬링합니다.  
  
-   이름 일치  
  
     <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=fullName> 필드가 [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)]에서의 기본값인 **true**이면 플랫폼 호출은 사용자가 지정한 이름만 검색합니다.  예를 들어 사용자가 **MessageBox**를 지정하면 플랫폼 호출은 **MessageBox**를 검색하며 이 문자와 정확하게 일치하는 이름이 없으면 실패합니다.  
  
     반면 **ExactSpelling** 필드가 **false**이면\(C\+\+ 및 C\#에서의 기본값\) 플랫폼 호출은 먼저 형식 비표시 별칭\(**MessageBox**\)을 검색하고 해당 별칭이 없으면 형식 표시 이름\(**MessageBoxA**\)을 검색합니다.  ANSI 이름 일치 동작은 유니코드 이름 일치 동작과는 다릅니다.  
  
 **CharSet.Unicode**  
  
-   문자열 마샬링  
  
     플랫폼 호출은 관리되는 형식\(유니코드\)의 문자열을 유니코드 형식에 복사합니다.  
  
-   이름 일치  
  
     **ExactSpelling** 필드가 **true**\([!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)]에서의 기본값\)이면 플랫폼 호출은 사용자가 지정한 이름만 검색합니다.  예를 들어, 사용자가 **MessageBox**를 지정하면 플랫폼 호출은 **MessageBox**를 검색하며 이 문자와 정확하게 일치하는 이름이 없으면 실패합니다.  
  
     반면 **ExactSpelling** 필드가 **false**이면\(C\+\+ 및 C\#에서의 기본값\) 플랫폼 호출은 먼저 형식 표시 이름\(**MessageBoxW**\)을 검색하고 해당 이름이 없으면 형식 비표시 별칭\(**MessageBox**\)을 검색합니다.  유니코드 이름 일치 동작은 ANSI 이름 일치 동작과는 다릅니다.  
  
 **CharSet.Auto**  
  
-   플랫폼 호출은 대상 플랫폼에 따라 런타임에 ANSI와 유니코드 형식 중에서 선택합니다.  
  
## Visual Basic에서 문자 집합 지정  
 다음 예제에서는 **MessageBox** 함수를 세 번 선언하는데, 선언할 때마다 문자 집합 동작이 다릅니다.  Visual Basic에서 **Ansi**, **Unicode** 또는 **Auto** 키워드를 선언문에 추가하여 문자 집합 동작을 지정할 수 있습니다.  
  
 처음 선언문에서처럼 문자 집합 키워드를 생략하면 <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=fullName> 필드의 기본값이 ANSI 문자 집합이 됩니다.  예제의 둘째 및 셋째 선언문에서는 키워드를 사용하여 문자 집합을 명시적으로 지정합니다.  
  
```vb  
Imports System.Runtime.InteropServices  
  
Public Class Win32  
   Declare Function MessageBoxA Lib "user32.dll"(ByVal hWnd As Integer, _  
       ByVal txt As String, ByVal caption As String, _  
       ByVal Typ As Integer) As Integer  
  
   Declare Unicode Function MessageBoxW Lib "user32.dll" _  
       (ByVal hWnd As Integer, ByVal txt As String, _  
        ByVal caption As String, ByVal Typ As Integer) As Integer  
  
   Declare Auto Function MessageBox Lib "user32.dll" _  
       (ByVal hWnd As Integer, ByVal txt As String, _  
        ByVal caption As String, ByVal Typ As Integer) As Integer  
End Class  
```  
  
## C\# 및 C\+\+에서 문자 집합 지정  
 <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=fullName> 필드는 내부 문자 집합을 ANSI 또는 유니코드로 식별합니다.  문자 집합은 메서드에 대한 문자열 인수가 마샬링되는 방법을 제어합니다.  다음 폼 중 하나를 사용하여 문자 집합을 지정할 수 있습니다.  
  
```csharp  
[DllImport("dllname", CharSet=CharSet.Ansi)]  
[DllImport("dllname", CharSet=CharSet.Unicode)]  
[DllImport("dllname", CharSet=CharSet.Auto)]  
  
```  
  
```cpp  
[DllImport("dllname", CharSet=CharSet::Ansi)]  
[DllImport("dllname", CharSet=CharSet::Unicode)]  
[DllImport("dllname", CharSet=CharSet::Auto)]  
```  
  
 다음 예제에서는 문자 집합을 지정하는 데 사용되는 **MessageBox** 함수의 세 가지 관리되는 정의를 보여 줍니다.  첫째 정의에서는 문자 집합 정의가 생략되었으므로 **CharSet** 필드에 ANSI 문자 집합이 자동으로 사용됩니다.  
  
```csharp  
[DllImport("user32.dll")]  
    public static extern int MessageBoxA(int hWnd, String text,   
        String caption, uint type);  
[DllImport("user32.dll", CharSet=CharSet.Unicode)]  
    public static extern int MessageBoxW(int hWnd, String text,   
        String caption, uint type);  
[DllImport("user32.dll", CharSet=CharSet.Auto)]  
    public static extern int MessageBox(int hWnd, String text,   
        String caption, uint type);  
  
```  
  
```cpp  
typedef void* HWND;  
  
//Can use MessageBox or MessageBoxA.  
[DllImport("user32")]  
extern "C" int MessageBox(HWND hWnd,  
                          String* pText,  
                          String* pCaption,  
                          unsigned int uType);  
  
//Can use MessageBox or MessageBoxW.  
[DllImport("user32", CharSet=CharSet::Unicode)]  
extern "C" int MessageBoxW(HWND hWnd,  
                          String* pText,  
                          String* pCaption,  
                          unsigned int uType);  
  
//Must use MessageBox.  
[DllImport("user32", CharSet=CharSet::Auto)]  
extern "C" int MessageBox(HWND hWnd,  
                          String* pText,  
                          String* pCaption,  
                          unsigned int uType);  
```  
  
## 참고 항목  
 <xref:System.Runtime.InteropServices.DllImportAttribute>   
 [관리 코드에서 프로토타입 만들기](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)   
 [플랫폼 호출 예제](../../../docs/framework/interop/platform-invoke-examples.md)   
 [플랫폼 호출을 사용하여 데이터 마샬링](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)