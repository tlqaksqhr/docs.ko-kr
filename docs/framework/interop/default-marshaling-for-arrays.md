---
title: "배열에 대한 기본 마샬링 | Microsoft Docs"
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
  - "배열, interop 마샬링"
  - "interop 마샬링, 배열"
ms.assetid: 8a3cca8b-dd94-4e3d-ad9a-9ee7590654bc
caps.latest.revision: 19
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 18
---
# 배열에 대한 기본 마샬링
관리 코드로만 구성된 응용 프로그램의 경우, 공용 언어 런타임에서는 배열 형식을 In\/Out 매개 변수로 전달합니다.  반면, interop 마샬러에서는 기본적으로 배열을 In 매개 변수로 전달합니다.  
  
 [고정 최적화](../../../docs/framework/interop/copying-and-pinning.md)를 사용하는 경우 blittable 배열은 동일한 아파트에 있는 개체와 상호 작용할 때 In\/Out 매개 변수로 작동하는 것처럼 보일 수 있습니다.  그러나 나중에 컴퓨터 간 프록시를 생성하는 데 사용되는 형식 라이브러리에 코드를 내보내는 경우 해당 라이브러리가 아파트 간의 호출을 마샬링하는 데 사용되면 해당 호출은 실제 In 매개 변수 동작으로 돌아갈 수 있습니다.  
  
 배열은 원래 복잡하며, 관리되는 배열과 관리되지 않는 배열의 차이를 이해하려면 다른 비 blittable 형식보다 더 많은 정보가 필요합니다.  이 항목에서는 배열 마샬링에 대한 다음 내용을 다룹니다.  
  
-   [관리되는 배열](#cpcondefaultmarshalingforarraysanchor1)  
  
-   [관리되지 않는 배열](#cpcondefaultmarshalingforarraysanchor2)  
  
-   [.NET 코드에 배열 매개 변수 전달](#cpcondefaultmarshalingforarraysanchor3)  
  
-   [COM에 배열 전달](#cpcondefaultmarshalingforarraysanchor4)  
  
<a name="cpcondefaultmarshalingforarraysanchor1"></a>   
## 관리되는 배열  
 관리되는 배열 형식은 다양할 수 있지만 <xref:System.Array?displayProperty=fullName> 클래스가 모든 배열 형식의 기본 클래스입니다.  **System.Array** 클래스에는 배열의 차수, 길이 및 하한\/상한을 결정하는 속성과, 배열에 액세스, 정렬, 검색, 복사 및 생성하는 메서드가 있습니다.  
  
 이러한 배열 형식은 동적이며 기본 클래스 라이브러리에 해당되는 정적 형식이 정의되어 있지 않습니다.  요소 형식과 차수의 각 조합을 서로 다른 배열 형식으로 생각하면 편리합니다.  따라서 정수의 1차원 배열은 double 형식의 1차원 배열과 형식이 다릅니다.  마찬가지로 정수의 2차원 배열은 정수의 1차원 배열과 다릅니다.  형식을 비교할 때 배열 경계는 고려되지 않습니다.  
  
 다음 표에서 보여 주는 것처럼, 관리되는 배열의 인스턴스에는 특정 요소 형식, 차수 및 하한이 있어야 합니다.  
  
|관리되는 배열 형식|요소 형식|차수|하한|시그니처 표기법|  
|----------------|-----------|--------|--------|--------------|  
|**ELEMENT\_TYPE\_ARRAY**|type으로 지정됨|rank로 지정됨|bounds로 지정됨\(선택적\)|*type* **\[** *n*,*m* **\]**|  
|**ELEMENT\_TYPE\_CLASS**|알 수 없음|알 수 없음|알 수 없음|**System.Array**|  
|**ELEMENT\_TYPE\_SZARRAY**|type으로 지정됨|1|0|*type* **\[** *n* **\]**|  
  
<a name="cpcondefaultmarshalingforarraysanchor2"></a>   
## 관리되지 않는 배열  
 관리되지 않는 배열은 COM 스타일의 안전 배열이거나 고정 또는 가변 길이의 C 스타일 배열입니다.  안전 배열은 연관된 배열 데이터의 형식, 차수 및 경계를 수반하는 자체 설명 배열입니다.  C 스타일 배열은 하한이 0으로 고정된 1차원 형식 배열입니다.  마샬링 서비스에서는 두 배열 형식 모두에 대한 지원을 제한합니다.  
  
<a name="cpcondefaultmarshalingforarraysanchor3"></a>   
## .NET 코드에 배열 매개 변수 전달  
 C 스타일 배열과 안전 배열 모두 비관리 코드에서 안전 배열 또는 C 스타일 배열 중 하나로 .NET 코드에 전달될 수 있습니다.  다음 표에서는 관리되지 않는 형식 값과 가져온 형식을 보여 줍니다.  
  
|관리되지 않는 형식|가져온 형식|  
|----------------|------------|  
|**SafeArray\(** *Type* **\)**|**ELEMENT\_TYPE\_SZARRAY** **\<**ConvertedType**\>**<br /><br /> 차수는 1이고 하한은 0입니다.  크기는 관리되는 시그니처에 제공되는 경우에만 알 수 있습니다.  차수가 1이 아니거나 하한이 0이 아닌 안전 배열은 **SZARRAY**로 마샬링될 수 없습니다.|  
|*Type*  **\[\]**|**ELEMENT\_TYPE\_SZARRAY** **\<**ConvertedType**\>**<br /><br /> 차수는 1이고 하한은 0입니다.  크기는 관리되는 시그니처에 제공되는 경우에만 알 수 있습니다.|  
  
### 안전 배열  
 형식 라이브러리에서 .NET 어셈블리로 안전 배열을 가져올 때 해당 배열은 **int**와 같은 알려진 형식의 1차원 배열로 변환됩니다.  매개 변수에 적용되는 동일한 형식 변환 규칙이 배열 요소에도 적용됩니다.  예를 들어, **BSTR** 형식의 안전 배열은 문자열의 관리되는 배열이 되고 variant의 안전 배열은 개체의 관리되는 배열이 됩니다.  **SAFEARRAY** 요소 형식은 형식 라이브러리에서 캡처되어 <xref:System.Runtime.InteropServices.UnmanagedType> 열거형의 **SAFEARRAY** 값에 저장됩니다.  
  
 형식 라이브러리에서 안전 배열의 차수와 범위를 확인할 수 없으므로 차수는 1로, 하한은 0으로 가정됩니다.  [형식 라이브러리 가져오기\(Tlbimp.exe\)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md)에서 생성하는 관리되는 시그니처에 차수와 범위를 정의해야 합니다.  런타임에 메서드에 전달된 차수가 다르면 <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException>이 throw됩니다.  런타임에 전달된 배열의 형식이 다르면 <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException>이 throw됩니다.  다음 예제에서는 관리 코드와 비관리 코드의 안전 배열을 보여 줍니다.  
  
 **관리되지 않는 시그니처**  
  
```  
HRESULT New1([in] SAFEARRAY( int ) ar);  
HRESULT New2([in] SAFEARRAY( DATE ) ar);  
HRESULT New3([in, out] SAFEARRAY( BSTR ) *ar);  
```  
  
 **관리되는 시그니처**  
  
```vb  
Sub New1(<MarshalAs(UnmanagedType.SafeArray, SafeArraySubType:=VT_I4)> _  
   ar() As Integer)  
Sub New2(<MarshalAs(UnmanagedType.SafeArray, SafeArraySubType:=VT_DATE)> _   
   ar() As DateTime)  
Sub New3(ByRef <MarshalAs(UnmanagedType.SafeArray, SafeArraySubType:=VT_BSTR)> _   
   ar() As String)  
  
```  
  
```csharp  
void New1([MarshalAs(UnmanagedType.SafeArray, SafeArraySubType=VT_I4)] int[] ar) ;  
void New2([MarshalAs(UnmanagedType.SafeArray, SafeArraySubType=VT_DATE)]   
   DateTime[] ar);  
void New3([MarshalAs(UnmanagedType.SafeArray, SafeArraySubType=VT_BSTR)]   
   ref String[] ar);  
```  
  
 다차원 또는 0에서 시작하지 않는 안전 배열은 Tlbimp.exe에서 생성한 메서드 시그니처를 수정하여 **ELEMENT\_TYPE\_SZARRAY** 대신 **ELEMENT\_TYPE\_ARRAY**의 요소 형식을 나타내도록 한 경우에 관리 코드로 마샬링될 수 있습니다.  또는 Tlbimp.exe와 **\/sysarray** 스위치를 사용하여 모든 배열을 <xref:System.Array?displayProperty=fullName> 개체로 가져올 수 있습니다.  전달되는 배열이 다차원으로 인식되는 경우에는 Tlbimp.exe에서 생성한 MSIL\(Microsoft Intermediate Language\) 코드를 편집한 다음 다시 컴파일할 수 있습니다.  MSIL 코드 수정 방법에 대한 자세한 내용은 [런타임 호출 가능 래퍼 사용자 지정](http://msdn.microsoft.com/ko-kr/4652beaf-77d0-4f37-9687-ca193288c0be)을 참조하십시오.  
  
### C 스타일 배열  
 형식 라이브러리에서 .NET 어셈블리로 C 스타일 배열을 가져올 때 해당 배열은 **ELEMENT\_TYPE\_SZARRAY**로 변환됩니다.  
  
 배열 요소 형식은 형식 라이브러리에서 확인되며 가져오는 동안 그대로 유지됩니다.  매개 변수에 적용되는 동일한 변환 규칙이 배열 요소에도 적용됩니다.  예를 들어, **LPStr** 형식의 배열은 **String** 형식의 배열이 됩니다.  Tlbimp.exe에서는 배열 요소 형식을 캡처하고 매개 변수에 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성을 적용합니다.  
  
 배열 차수는 1인 것으로 가정됩니다.  차수가 1보다 크면 배열은 열 우선 순서의 1차원 배열로 마샬링됩니다.  하한은 항상 0입니다.  
  
 형식 라이브러리에는 고정 또는 가변 길이의 배열이 포함될 수 있습니다.  형식 라이브러리에는 가변 길이의 배열을 마샬링하는 데 필요한 정보가 없으므로 Tlbimp.exe에서는 형식 라이브러리에서 고정 길이의 배열만 가져올 수 있습니다.  고정 길이의 배열인 경우, 크기는 형식 라이브러리에서 가져오고 매개 변수에 적용되는 **MarshalAsAttribute**에서 캡처됩니다.  
  
 가변 길이의 배열이 포함된 형식 라이브러리는 다음 예제에서처럼 사용자가 직접 정의해야 합니다.  
  
 **관리되지 않는 시그니처**  
  
```  
HRESULT New1(int ar[10]);  
HRESULT New2(double ar[10][20]);  
HRESULT New3(LPWStr ar[10]);  
```  
  
 **관리되는 시그니처**  
  
```vb  
Sub New1(<MarshalAs(UnmanagedType.LPArray, SizeConst=10)> _  
   ar() As Integer)  
Sub New2(<MarshalAs(UnmanagedType.LPArray, SizeConst=200)> _  
   ar() As Double)  
Sub New2(<MarshalAs(UnmanagedType.LPArray, _  
   ArraySubType=UnmanagedType.LPWStr, SizeConst=10)> _  
   ar() As String)  
  
```  
  
```csharp  
void New1([MarshalAs(UnmanagedType.LPArray, SizeConst=10)] int[] ar);  
void New2([MarshalAs(UnmanagedType.LPArray, SizeConst=200)] double[] ar);  
void New2([MarshalAs(UnmanagedType.LPArray,   
   ArraySubType=UnmanagedType.LPWStr, SizeConst=10)] String[] ar);  
```  
  
 IDL\(Interface Definition Language\) 소스에서 배열에 **size\_is** 또는 **length\_is** 특성을 적용하여 클라이언트에 크기를 전달할 수 있지만, MIDL\(Microsoft Interface Definition Language\) 컴파일러에서는 해당 정보를 형식 라이브러리에 전파하지 않습니다.  크기를 모르면 interop 마샬링 서비스에서 배열 요소를 마샬링할 수 없습니다.  따라서 가변 길이의 배열은 참조 인수로 가져오게 됩니다.  예를 들면 다음과 같습니다.  
  
 **관리되지 않는 시그니처**  
  
```  
HRESULT New1(int ar[]);  
HRESULT New2(int ArSize, [size_is(ArSize)] double ar[]);  
HRESULT New3(int ElemCnt, [length_is(ElemCnt)] LPStr ar[]);  
```  
  
 **관리되는 시그니처**  
  
```vb  
Sub New1(ByRef ar As Integer)  
Sub New2(ByRef ar As Double)  
Sub New3(ByRef ar As String)  
  
```  
  
```csharp  
void New1(ref int ar);    
void New2(ref double ar);    
void New3(ref String ar);   
```  
  
 Tlbimp.exe에서 생성한 MSIL\(Microsoft Intermediate Language\) 코드를 편집한 다음 다시 컴파일하여 마샬러에 배열 크기를 제공할 수 있습니다.  MSIL 코드 수정 방법에 대한 자세한 내용은 [런타임 호출 가능 래퍼 사용자 지정](http://msdn.microsoft.com/ko-kr/4652beaf-77d0-4f37-9687-ca193288c0be)을 참조하십시오.  배열에 있는 요소의 개수를 나타내려면 다음 중 한 가지 방법으로 관리되는 메서드 정의의 배열 매개 변수에 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 형식을 적용합니다.  
  
-   배열에 있는 요소의 개수가 포함된 다른 매개 변수를 지정합니다.  이 매개 변수는 위치로 식별되며 첫 번째 매개 변수는 0에서 시작합니다.  \[Visual Basic\]  
  
    ```vb  
    Sub [New](ElemCnt As Integer, _  
       <MarshalAs(UnmanagedType.LPArray, SizeParamIndex:=1)> _  
       ar() As Integer)  
  
    ```  
  
    ```csharp  
    void New(  
       int ElemCnt,   
       [MarshalAs(UnmanagedType.LPArray, SizeParamIndex=0)] int[] ar );  
    ```  
  
-   배열 크기를 상수로 정의합니다.  예를 들면 다음과 같습니다.  
  
    ```vb  
    Sub [New](<MarshalAs(UnmanagedType.LPArray, SizeConst:=128)> _  
       ar() As Integer)  
  
    ```  
  
    ```csharp  
    void New(  
       [MarshalAs(UnmanagedType.LPArray, SizeConst=128)] int[] ar );  
    ```  
  
 비관리 코드에서 관리 코드로 배열을 마샬링할 때 마샬러에서는 매개 변수와 연관된 **MarshalAsAttribute**를 검사하여 배열 크기를 확인합니다.  배열 크기가 지정되지 않았으면 한 요소만 마샬링됩니다.  
  
> [!NOTE]
>  **MarshalAsAttribute**는 관리되는 배열을 비관리 코드로 마샬링하는 데 영향을 주지 않습니다.  이 방향으로 마샬링할 때 배열 크기는 검사를 통해 확인됩니다.  관리되는 배열의 하위 집합은 마샬링할 수 없습니다.  
  
 interop 마샬러에서는 **CoTaskMemAlloc** 및 **CoTaskMemFree** 메서드를 사용하여 메모리를 할당하고 검색합니다.  비관리 코드에서 수행하는 메모리 할당에도 이 메서드가 사용되어야 합니다.  
  
<a name="cpcondefaultmarshalingforarraysanchor4"></a>   
## COM에 배열 전달  
 모든 관리되는 배열 형식은 관리 코드에서 비관리 코드로 전달될 수 있습니다.  다음 표에서 보여 주는 것처럼 관리되는 형식과 해당 형식에 적용된 특성에 따라 안전 배열 또는 C 스타일 배열로 배열에 액세스할 수 있습니다.  
  
|관리되는 배열 형식|내보내는 형식|  
|----------------|-------------|  
|**ELEMENT\_TYPE\_SZARRAY** **\<**type**\>**|<xref:System.Runtime.InteropServices.UnmanagedType> **.SafeArray\(** *type* **\)**<br /><br /> **UnmanagedType.LPArray**<br /><br /> 형식은 시그니처에서 제공합니다.  차수는 항상 1이고 하한은 항상 0이며  크기는 항상 런타임에 인식됩니다.|  
|**ELEMENT\_TYPE\_ARRAY** **\<**type**\>** **\<**rank**\>**\[**\<**bounds**\>**\]|**UnmanagedType.SafeArray\(** *type* **\)**<br /><br /> **UnmanagedType.LPArray**<br /><br /> 형식, 차수, 경계는 시그니처에서 제공합니다.  크기는 항상 런타임에 인식됩니다.|  
|**ELEMENT\_TYPE\_CLASS** **\<**<xref:System.Array?displayProperty=fullName>**\>**|**UT\_Interface**<br /><br /> **UnmanagedType.SafeArray\(** *type* **\)**<br /><br /> 형식, 차수, 경계 및 크기는 항상 런타임에 인식됩니다.|  
  
 LPSTR 또는 LPWSTR을 포함하는 구조의 배열과 관련된 OLE 자동화에는 제한 사항이 있습니다.  따라서 **String** 필드는 **UnmanagedType.BSTR**로 마샬링되어야 합니다.  그렇지 않으면 예외가 throw됩니다.  
  
### ELEMENT\_TYPE\_SZARRAY  
 **ELEMENT\_TYPE\_SZARRAY** 매개 변수\(1차원 배열\)를 포함하는 메서드를 .NET 어셈블리에서 형식 라이브러리로 내보내면 해당 배열 매개 변수는 주어진 형식의 **SAFEARRAY**로 변환됩니다.  동일한 변환 규칙이 배열 요소 형식에 적용됩니다.  관리되는 배열의 내용은 자동으로 관리되는 메모리에서 **SAFEARRAY**로 복사됩니다.  예를 들면 다음과 같습니다.  
  
#### 관리되는 시그니처  
  
```vb  
Sub [New](ar() As Long)  
Sub [New](ar() As String)  
  
```  
  
```csharp  
void New(long[] ar );  
void New(String[] ar );  
```  
  
#### 관리되지 않는 시그니처  
  
```  
HRESULT New([in] SAFEARRAY( long ) ar);   
HRESULT New([in] SAFEARRAY( BSTR ) ar);  
```  
  
 안전 배열의 차수는 항상 1이며 하한은 항상 0입니다.  크기는 관리되는 배열이 전달될 때 해당 배열의 크기를 통해 런타임에 확인됩니다.  
  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성을 사용하면 배열을 C 스타일 배열로 마샬링할 수도 있습니다.  예를 들면 다음과 같습니다.  
  
#### 관리되는 시그니처  
  
```vb  
Sub [New](<MarshalAs(UnmanagedType.LPArray, SizeParamIndex:=1)> _  
   ar() As Long, size as Integer)  
Sub [New](<MarshalAs(UnmanagedType.LPArray, SizeParamIndex:=1)> _  
   ar() As String, size as Integer)  
Sub [New](<MarshalAs(UnmanagedType.LPArray, _  
   ArraySubType= UnmanagedType.LPStr, SizeParamIndex:=1)> _  
   ar() As String, size as Integer)  
  
```  
  
```csharp  
void New([MarshalAs(UnmanagedType.LPArray, SizeParamIndex=1)]   
   long [] ar, int size );  
void New([MarshalAs(UnmanagedType.LPArray, SizeParamIndex=1)]   
   String [] ar, int size );  
void New([MarshalAs(UnmanagedType.LPArray, ArraySubType=   
   UnmanagedType.LPStr, SizeParamIndex=1)]   
   String [] ar, int size );  
```  
  
#### 관리되지 않는 시그니처  
  
```  
HRESULT New(long ar[]);   
HRESULT New(BSTR ar[]);   
HRESULT New(LPStr ar[]);  
```  
  
 마샬러에는 배열을 마샬링하는 데 필요한 길이 정보가 있지만, 배열 길이는 대개 호출 수신자에게 길이를 전달하는 별도의 인수로 전달됩니다.  
  
### ELEMENT\_TYPE\_ARRAY  
 **ELEMENT\_TYPE\_ARRAY** 매개 변수가 포함된 메서드를 .NET 어셈블리에서 형식 라이브러리로 내보낼 때 해당 배열 매개 변수는 주어진 형식의 **SAFEARRAY**로 변환됩니다.  관리되는 배열의 내용은 자동으로 관리되는 메모리에서 **SAFEARRAY**로 복사됩니다.  예를 들면 다음과 같습니다.  
  
#### 관리되는 시그니처  
  
```vb  
Sub [New](ar(,) As Long)  
Sub [New](ar(,) As String)  
  
```  
  
```csharp  
void New( long [,] ar );  
void New( String [,] ar );  
```  
  
#### 관리되지 않는 시그니처  
  
```  
HRESULT New([in] SAFEARRAY( long ) ar);   
HRESULT New([in] SAFEARRAY( BSTR ) ar);  
```  
  
 안전 배열의 차수, 크기 및 경계는 관리되는 배열의 특징을 통해 런타임에 확인됩니다.  
  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성을 적용하면 배열을 C 스타일 배열로 마샬링할 수도 있습니다.  예를 들면 다음과 같습니다.  
  
#### 관리되는 시그니처  
  
```vb  
Sub [New](<MarshalAs(UnmanagedType.LPARRAY, SizeParamIndex:=1)> _  
   ar(,) As Long, size As Integer)  
Sub [New](<MarshalAs(UnmanagedType.LPARRAY, _  
   ArraySubType:=UnmanagedType.LPStr, SizeParamIndex:=1)> _  
   ar(,) As String, size As Integer)  
  
```  
  
```csharp  
void New([MarshalAs(UnmanagedType.LPARRAY, SizeParamIndex=1)]   
   long [,] ar, int size );  
void New([MarshalAs(UnmanagedType.LPARRAY,   
   ArraySubType= UnmanagedType.LPStr, SizeParamIndex=1)]   
   String [,] ar, int size );  
```  
  
#### 관리되지 않는 시그니처  
  
```  
HRESULT New(long ar[]);   
HRESULT New(LPStr ar[]);  
```  
  
 중첩 배열은 마샬링할 수 없습니다.  예를 들어, 다음 시그니처는 [형식 라이브러리 내보내기\(Tlbexp.exe\)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)를 사용하여 내보낼 때 오류를 발생시킵니다.  
  
#### 관리되는 시그니처  
  
```vb  
Sub [New](ar()()() As Long)  
  
```  
  
```csharp  
void New(long [][][] ar );  
```  
  
### ELEMENT\_TYPE\_CLASS \<System.Array\>  
 <xref:System.Array?displayProperty=fullName> 매개 변수가 포함된 메서드를 .NET 어셈블리에서 형식 라이브러리로 내보낼 때 해당 배열 매개 변수는 **\_Array** 인터페이스로 변환됩니다.  관리되는 배열의 내용은 **\_Array** 인터페이스의 메서드 및 속성을 통해서만 액세스할 수 있습니다.  <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성을 사용하면 **System.Array**를 **SAFEARRAY**로 마샬링할 수도 있습니다.  안전 배열로 마샬링될 때 배열 요소는 variant로 마샬링됩니다.  예를 들면 다음과 같습니다.  
  
#### 관리되는 시그니처  
  
```vb  
Sub New1( ar As System.Array )  
Sub New2( <MarshalAs(UnmanagedType.Safe array)> ar As System.Array )  
  
```  
  
```csharp  
void New1( System.Array ar );  
void New2( [MarshalAs(UnmanagedType.Safe array)] System.Array ar );  
```  
  
#### 관리되지 않는 시그니처  
  
```  
HRESULT New([in] _Array *ar);   
HRESULT New([in] SAFEARRAY(VARIANT) ar);  
```  
  
### 구조체 내의 배열  
 관리되지 않는 구조체에는 포함 배열이 들어 있을 수 있습니다.  기본적으로 이 포함 배열 필드는 SAFEARRAY로 마샬링됩니다.  다음 예제에서 `s1`은 구조체 자체 내에 직접 할당된 포함 배열입니다.  
  
#### 관리되지 않는 표현  
  
```  
struct MyStruct {  
    short s1[128];  
}  
```  
  
 배열을 [UnmanagedType.ByValArray](frlrfSystemRuntimeInteropServicesUnmanagedTypeClassTopic)로 마샬링할 수 있습니다. 이 경우 [MarshalAsAttribute.SizeConst](frlrfSystemRuntimeInteropServicesMarshalAsAttributeClassTopic) 필드를 설정해야 합니다.  크기는 상수로만 설정될 수 있습니다.  다음 코드에서는  `MyStruct`의 관리되는 정의를 보여 줍니다.  
  
```vb  
Public Structure <StructLayout(LayoutKind.Sequential)> MyStruct  
   Public <MarshalAs(UnmanagedType.ByValArray, SizeConst := 128)> _  
     s1() As Short  
End Structure  
  
```  
  
```csharp  
[StructLayout(LayoutKind.Sequential)]  
public struct MyStruct {  
   [MarshalAs(UnmanagedType.ByValArray, SizeConst=128)] public short[] s1;  
}  
```  
  
## 참고 항목  
 [기본 마샬링 동작](../../../docs/framework/interop/default-marshaling-behavior.md)   
 [Blittable 형식 및 비 Blittable 형식](../../../docs/framework/interop/blittable-and-non-blittable-types.md)   
 [Directional Attributes](http://msdn.microsoft.com/ko-kr/241ac5b5-928e-4969-8f58-1dbc048f9ea2)   
 [복사 및 고정](../../../docs/framework/interop/copying-and-pinning.md)