---
title: "개체에 대한 마샬링 | Microsoft Docs"
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
  - "interop 마샬링, 개체"
  - "개체, interop 마샬링"
ms.assetid: c2ef0284-b061-4e12-b6d3-6a502b9cc558
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# 개체에 대한 마샬링
<xref:System.Object?displayProperty=fullName>로 형식화된 매개 변수 및 필드는 다음 중 한 가지 형식으로 비관리 코드에 노출될 수 있습니다.  
  
-   variant \- 개체가 매개 변수인 경우  
  
-   인터페이스 \- 개체가 구조체 필드인 경우  
  
 COM interop만 개체 형식에 대한 마샬링을 지원합니다.  기본 동작은 개체를 COM variant로 마샬링하는 것입니다.  이 규칙은 **Object** 형식에만 적용되며 **Object** 클래스에서 파생된 강력한 형식의 개체에는 적용되지 않습니다.  
  
 이 항목에서는 개체 형식 마샬링에 대한 다음과 같은 추가 정보를 제공합니다.  
  
-   [마샬링 옵션](#cpcondefaultmarshalingforobjectsanchor7)  
  
-   [개체를 인터페이스로 마샬링](#cpcondefaultmarshalingforobjectsanchor2)  
  
-   [개체를 Variant로 마샬링](#cpcondefaultmarshalingforobjectsanchor3)  
  
-   [Variant를 개체로 마샬링](#cpcondefaultmarshalingforobjectsanchor4)  
  
-   [ByRef Variant 마샬링](#cpcondefaultmarshalingforobjectsanchor6)  
  
<a name="cpcondefaultmarshalingforobjectsanchor7"></a>   
## 마샬링 옵션  
 다음 표에서는 **Object** 데이터 형식의 마샬링 옵션을 보여 줍니다.  <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성은 개체를 마샬링하기 위한 몇 개의 <xref:System.Runtime.InteropServices.UnmanagedType> 열거형 값을 제공합니다.  
  
|열거형|관리되지 않는 형식의 설명|  
|---------|--------------------|  
|**UnmanagedType.Struct**<br /><br /> \(매개 변수 기본값\)|COM 스타일 variant|  
|**UnmanagedType.Interface**|가능하면 **IDispatch** 인터페이스이고, 그렇지 않으면 **IUnknown** 인터페이스|  
|**UnmanagedType.IUnknown**<br /><br /> \(필드 기본값\)|**IUnknown** 인터페이스|  
|**UnmanagedType.IDispatch**|**IDispatch** 인터페이스|  
  
 다음 예제에서는 `MarshalObject`의 관리되는 인터페이스 정의를 보여 줍니다.  
  
```vb  
Interface MarshalObject  
   Sub SetVariant(o As Object)  
   Sub SetVariantRef(ByRef o As Object)  
   Function GetVariant() As Object  
  
   Sub SetIDispatch( <MarshalAs(UnmanagedType.IDispatch)> o As Object)  
   Sub SetIDispatchRef(ByRef <MarshalAs(UnmanagedType.IDispatch)> o _  
      As Object)  
   Function GetIDispatch() As <MarshalAs(UnmanagedType.IDispatch)> Object  
   Sub SetIUnknown( <MarshalAs(UnmanagedType.IUnknown)> o As Object)  
   Sub SetIUnknownRef(ByRef <MarshalAs(UnmanagedType.IUnknown)> o _  
      As Object)  
   Function GetIUnknown() As <MarshalAs(UnmanagedType.IUnknown)> Object  
End Interface  
  
```  
  
```csharp  
interface MarshalObject {  
   void SetVariant(Object o);  
   void SetVariantRef(ref Object o);  
   Object GetVariant();  
  
   void SetIDispatch ([MarshalAs(UnmanagedType.IDispatch)]Object o);  
   void SetIDispatchRef([MarshalAs(UnmanagedType.IDispatch)]ref Object o);  
   [MarshalAs(UnmanagedType.IDispatch)] Object GetIDispatch();  
   void SetIUnknown ([MarshalAs(UnmanagedType.IUnknown)]Object o);  
   void SetIUnknownRef([MarshalAs(UnmanagedType.IUnknown)]ref Object o);  
   [MarshalAs(UnmanagedType.IUnknown)] Object GetIUnknown();  
}  
```  
  
 다음 코드에서는 `MarshalObject` 인터페이스를 형식 라이브러리로 내보냅니다.  
  
```  
interface MarshalObject {  
   HRESULT SetVariant([in] VARIANT o);  
   HRESULT SetVariantRef([in,out] VARIANT *o);  
   HRESULT GetVariant([out,retval] VARIANT *o)   
   HRESULT SetIDispatch([in] IDispatch *o);  
   HRESULT SetIDispatchRef([in,out] IDispatch **o);  
   HRESULT GetIDispatch([out,retval] IDispatch **o)   
   HRESULT SetIUnknown([in] IUnknown *o);  
   HRESULT SetIUnknownRef([in,out] IUnknown **o);  
   HRESULT GetIUnknown([out,retval] IUnknown **o)   
}  
```  
  
> [!NOTE]
>  interop 마샬러에서는 호출 후 자동으로 variant 내의 할당된 개체를 해제합니다.  
  
 다음 예제에서는 formatted 값 형식을 보여 줍니다.  
  
```vb  
Public Structure ObjectHolder  
   Dim o1 As Object  
   <MarshalAs(UnmanagedType.IDispatch)> Public o2 As Object  
End Structure  
  
```  
  
```csharp  
public struct ObjectHolder {  
   Object o1;  
   [MarshalAs(UnmanagedType.IDispatch)]public Object o2;  
}  
```  
  
 다음 코드에서는 formatted 형식을 형식 라이브러리로 내보냅니다.  
  
```  
struct ObjectHolder {  
   VARIANT o1;  
   IDispatch *o2;  
}  
```  
  
<a name="cpcondefaultmarshalingforobjectsanchor2"></a>   
## 개체를 인터페이스로 마샬링  
 개체를 인터페이스로 COM에 노출할 때 해당 인터페이스는 관리되는 형식 <xref:System.Object>에 대한 클래스 인터페이스\(**\_Object** 인터페이스\)입니다.  이 인터페이스는 결과 형식 라이브러리에서 **IDispatch**\([UnmanagedType.IDispatch](frlrfSystemRuntimeInteropServicesUnmanagedTypeClassTopic)\) 또는 **IUnknown**\(**UnmanagedType.IUnknown**\)으로 형식화됩니다.  COM 클라이언트에서는 관리되는 클래스의 멤버 또는 파생 클래스에서 **\_Object** 인터페이스를 통해 구현된 멤버를 동적으로 호출할 수 있습니다.  또한 클라이언트에서는 **QueryInterface**를 호출하여 관리되는 형식에 의해 명시적으로 구현된 다른 인터페이스를 가져올 수도 있습니다.  
  
<a name="cpcondefaultmarshalingforobjectsanchor3"></a>   
## 개체를 Variant로 마샬링  
 개체를 variant로 마샬링할 때 내부 variant 형식은 런타임에 다음 규칙에 따라 결정됩니다.  
  
-   개체 참조가 null\(Visual Basic에서는 **Nothing**\)이면 해당 개체는 **VT\_EMPTY** 형식의 variant로 마샬링됩니다.  
  
-   개체가 다음 표에 열거된 형식의 인스턴스이면 결과 variant 형식은 표에서 보여 주는 것처럼 마샬러에 빌드된 규칙에 따라 결정됩니다.  
  
-   마샬링 동작을 명시적으로 제어해야 하는 다른 개체는 <xref:System.IConvertible> 인터페이스를 구현할 수 있습니다.  이 경우 variant 형식은 <xref:System.IConvertible.GetTypeCode%2A?displayProperty=fullName> 메서드에서 반환된 형식 코드에 따라 결정됩니다.  그렇지 않으면 개체는 **VT\_UNKNOWN** 형식의 variant로 마샬링됩니다.  
  
### 시스템 형식을 Variant로 마샬링  
 다음 표에서는 관리되는 개체 형식과 이에 대응하는 COM variant 형식을 보여 줍니다.  이러한 형식은 호출되는 메서드의 시그니처 형식이 <xref:System.Object?displayProperty=fullName>인 경우에만 변환됩니다.  
  
|개체 형식|COM variant 형식|  
|-----------|--------------------|  
|Null 개체 참조\(Visual Basic에서는 **Nothing**\)입니다.|**VT\_EMPTY**|  
|<xref:System.DBNull?displayProperty=fullName>|**VT\_NULL**|  
|<xref:System.Runtime.InteropServices.ErrorWrapper?displayProperty=fullName>|**VT\_ERROR**|  
|<xref:System.Reflection.Missing?displayProperty=fullName>|**E\_PARAMNOTFOUND**가 포함된 **VT\_ERROR**|  
|<xref:System.Runtime.InteropServices.DispatchWrapper?displayProperty=fullName>|**VT\_DISPATCH**|  
|<xref:System.Runtime.InteropServices.UnknownWrapper?displayProperty=fullName>|**VT\_UNKNOWN**|  
|<xref:System.Runtime.InteropServices.CurrencyWrapper?displayProperty=fullName>|**VT\_CY**|  
|<xref:System.Boolean?displayProperty=fullName>|**VT\_BOOL**|  
|<xref:System.SByte?displayProperty=fullName>|**VT\_I1**|  
|<xref:System.Byte?displayProperty=fullName>|**VT\_UI1**|  
|<xref:System.Int16?displayProperty=fullName>|**VT\_I2**|  
|<xref:System.UInt16?displayProperty=fullName>|**VT\_UI2**|  
|<xref:System.Int32?displayProperty=fullName>|**VT\_I4**|  
|<xref:System.UInt32?displayProperty=fullName>|**VT\_UI4**|  
|<xref:System.Int64?displayProperty=fullName>|**VT\_I8**|  
|<xref:System.UInt64?displayProperty=fullName>|**VT\_UI8**|  
|<xref:System.Single?displayProperty=fullName>|**VT\_R4**|  
|<xref:System.Double?displayProperty=fullName>|**VT\_R8**|  
|<xref:System.Decimal?displayProperty=fullName>|**VT\_DECIMAL**|  
|<xref:System.DateTime?displayProperty=fullName>|**VT\_DATE**|  
|<xref:System.String?displayProperty=fullName>|**VT\_BSTR**|  
|<xref:System.IntPtr?displayProperty=fullName>|**VT\_INT**|  
|<xref:System.UIntPtr?displayProperty=fullName>|**VT\_UINT**|  
|<xref:System.Array?displayProperty=fullName>|**VT\_ARRAY**|  
  
 다음 코드 예제에서는 앞의 예제에 정의된 `MarshalObject` 인터페이스를 사용하여 COM 서버에 다양한 variant 형식을 전달하는 방법을 보여 줍니다.  
  
```vb  
Dim mo As New MarshalObject()  
mo.SetVariant(Nothing)         ' Marshal as variant of type VT_EMPTY.  
mo.SetVariant(System.DBNull.Value) ' Marshal as variant of type VT_NULL.  
mo.SetVariant(CInt(27))        ' Marshal as variant of type VT_I2.  
mo.SetVariant(CLng(27))        ' Marshal as variant of type VT_I4.  
mo.SetVariant(CSng(27.0))      ' Marshal as variant of type VT_R4.  
mo.SetVariant(CDbl(27.0))      ' Marshal as variant of type VT_R8.  
  
```  
  
```csharp  
MarshalObject mo = new MarshalObject();  
mo.SetVariant(null);            // Marshal as variant of type VT_EMPTY.  
mo.SetVariant(System.DBNull.Value); // Marshal as variant of type VT_NULL.  
mo.SetVariant((int)27);          // Marshal as variant of type VT_I2.  
mo.SetVariant((long)27);          // Marshal as variant of type VT_I4.  
mo.SetVariant((single)27.0);   // Marshal as variant of type VT_R4.  
mo.SetVariant((double)27.0);   // Marshal as variant of type VT_R8.  
```  
  
 관리되는 해당 형식이 없는 COM 형식은 <xref:System.Runtime.InteropServices.ErrorWrapper>, <xref:System.Runtime.InteropServices.DispatchWrapper>, <xref:System.Runtime.InteropServices.UnknownWrapper>, <xref:System.Runtime.InteropServices.CurrencyWrapper> 등의 래퍼 클래스를 사용하여 마샬링될 수 있습니다.  다음 코드 예제에서는 이러한 래퍼를 사용하여 COM 서버에 다양한 variant 형식을 전달하는 방법을 보여 줍니다.  
  
```vb  
Imports System.Runtime.InteropServices  
' Pass inew as a variant of type VT_UNKNOWN interface.  
mo.SetVariant(New UnknownWrapper(inew))  
' Pass inew as a variant of type VT_DISPATCH interface.  
mo.SetVariant(New DispatchWrapper(inew))  
' Pass a value as a variant of type VT_ERROR interface.  
mo.SetVariant(New ErrorWrapper(&H80054002))  
' Pass a value as a variant of type VT_CURRENCY interface.  
mo.SetVariant(New CurrencyWrapper(New Decimal(5.25)))  
  
```  
  
```csharp  
using System.Runtime.InteropServices;  
// Pass inew as a variant of type VT_UNKNOWN interface.  
mo.SetVariant(new UnknownWrapper(inew));  
// Pass inew as a variant of type VT_DISPATCH interface.  
mo.SetVariant(new DispatchWrapper(inew));  
// Pass a value as a variant of type VT_ERROR interface.  
mo.SetVariant(new ErrorWrapper(0x80054002));  
// Pass a value as a variant of type VT_CURRENCY interface.  
mo.SetVariant(new CurrencyWrapper(new Decimal(5.25)));  
```  
  
 래퍼 클래스는 <xref:System.Runtime.InteropServices> 네임스페이스에 정의됩니다.  
  
### IConvertible 인터페이스를 Variant로 마샬링  
 앞 단원에 열거된 것 이외의 형식은 <xref:System.IConvertible> 인터페이스를 구현함으로써 해당 형식의 마샬링 방식을 제어할 수 있습니다.  개체가 **IConvertible** 인터페이스를 구현하는 경우 COM variant 형식은 런타임에 <xref:System.IConvertible.GetTypeCode%2A?displayProperty=fullName> 메서드에서 반환되는 <xref:System.TypeCode> 열거형의 값에 의해 결정됩니다.  
  
 다음 표에서는 **TypeCode** 열거형에 대해 가능한 값과 각 값에 대응하는 COM variant 형식을 보여 줍니다.  
  
|TypeCode|COM variant 형식|  
|--------------|--------------------|  
|**TypeCode.Empty**|**VT\_EMPTY**|  
|**TypeCode.Object**|**VT\_UNKNOWN**|  
|**TypeCode.DBNull**|**VT\_NULL**|  
|**TypeCode.Boolean**|**VT\_BOOL**|  
|**TypeCode.Char**|**VT\_UI2**|  
|**TypeCode.Sbyte**|**VT\_I1**|  
|**TypeCode.Byte**|**VT\_UI1**|  
|**TypeCode.Int16**|**VT\_I2**|  
|**TypeCode.UInt16**|**VT\_UI2**|  
|**TypeCode.Int32**|**VT\_I4**|  
|**TypeCode.UInt32**|**VT\_UI4**|  
|**TypeCode.Int64**|**VT\_I8**|  
|**TypeCode.UInt64**|**VT\_UI8**|  
|**TypeCode.Single**|**VT\_R4**|  
|**TypeCode.Double**|**VT\_R8**|  
|**TypeCode.Decimal**|**VT\_DECIMAL**|  
|**TypeCode.DateTime**|**VT\_DATE**|  
|**TypeCode.String**|**VT\_BSTR**|  
|지원되지 않습니다.|**VT\_INT**|  
|지원되지 않습니다.|**VT\_UINT**|  
|지원되지 않습니다.|**VT\_ARRAY**|  
|지원되지 않습니다.|**VT\_RECORD**|  
|지원되지 않습니다.|**VT\_CY**|  
|지원되지 않습니다.|**VT\_VARIANT**|  
  
 COM variant의 값은 **IConvertible.To** *Type* 인터페이스를 호출하여 결정됩니다. 여기서 **To** *Type*은 **IConvertible.GetTypeCode**에서 반환된 형식에 해당하는 변환 루틴입니다.  예를 들어, **IConvertible.GetTypeCode**에서 **TypeCode.Double**을 반환하는 개체는 **VT\_R8** 형식의 COM variant로 마샬링됩니다.  **IConvertible** 인터페이스로 캐스팅하고 <xref:System.IConvertible.ToDouble%2A> 메서드를 호출하면 COM variant의 **dblVal** 필드에 저장된 variant 값을 가져올 수 있습니다.  
  
<a name="cpcondefaultmarshalingforobjectsanchor4"></a>   
## Variant를 개체로 마샬링  
 variant를 개체로 마샬링할 때는 마샬링되는 variant의 형식 및 값에 따라 생성되는 개체의 형식이 결정됩니다.  다음 표에서는 각 variant 형식과, COM에서 .NET Framework로 variant가 전달될 때 마샬러에서 만드는 해당 개체 형식을 보여 줍니다.  
  
|COM variant 형식|개체 형식|  
|--------------------|-----------|  
|**VT\_EMPTY**|Null 개체 참조\(Visual Basic에서는 **Nothing**\)입니다.|  
|**VT\_NULL**|<xref:System.DBNull?displayProperty=fullName>|  
|**VT\_DISPATCH**|**System.\_\_ComObject**이거나, \(pdispVal \=\= null\)이면 null|  
|**VT\_UNKNOWN**|**System.\_\_ComObject**이거나, \(punkVal \=\= null\)이면 null|  
|**VT\_ERROR**|<xref:System.UInt32?displayProperty=fullName>|  
|**VT\_BOOL**|<xref:System.Boolean?displayProperty=fullName>|  
|**VT\_I1**|<xref:System.SByte?displayProperty=fullName>|  
|**VT\_UI1**|<xref:System.Byte?displayProperty=fullName>|  
|**VT\_I2**|<xref:System.Int16?displayProperty=fullName>|  
|**VT\_UI2**|<xref:System.UInt16?displayProperty=fullName>|  
|**VT\_I4**|<xref:System.Int32?displayProperty=fullName>|  
|**VT\_UI4**|<xref:System.UInt32?displayProperty=fullName>|  
|**VT\_I8**|<xref:System.Int64?displayProperty=fullName>|  
|**VT\_UI8**|<xref:System.UInt64?displayProperty=fullName>|  
|**VT\_R4**|<xref:System.Single?displayProperty=fullName>|  
|**VT\_R8**|<xref:System.Double?displayProperty=fullName>|  
|**VT\_DECIMAL**|<xref:System.Decimal?displayProperty=fullName>|  
|**VT\_DATE**|<xref:System.DateTime?displayProperty=fullName>|  
|**VT\_BSTR**|<xref:System.String?displayProperty=fullName>|  
|**VT\_INT**|<xref:System.Int32?displayProperty=fullName>|  
|**VT\_UINT**|<xref:System.UInt32?displayProperty=fullName>|  
|**VT\_ARRAY** &#124; **VT\_\***|<xref:System.Array?displayProperty=fullName>|  
|**VT\_CY**|<xref:System.Decimal?displayProperty=fullName>|  
|**VT\_RECORD**|해당되는 boxed 값 형식|  
|**VT\_VARIANT**|지원되지 않습니다.|  
  
 COM에서 관리 코드로 전달된 다음 다시 COM으로 전달된 variant는 호출 기간 동안 동일한 variant 형식을 유지하지 못 할 수 있습니다.  따라서 **VT\_DISPATCH** 형식의 variant가 COM에서 .NET Framework로 전달될 때 발생하는 사항을 고려해야 합니다.  마샬링 도중 variant는 <xref:System.Object?displayProperty=fullName>로 변환됩니다.  그런 다음 **Object**가 다시 COM으로 전달되면 해당 개체는 다시 **VT\_UNKNOWN** 형식의 variant로 마샬링됩니다.  개체가 관리 코드에서 COM으로 마샬링될 때 생성된 variant는 초기에 해당 개체를 생성하는 데 사용된 variant와 동일한 형식이 되지 않을 수도 있습니다.  
  
<a name="cpcondefaultmarshalingforobjectsanchor6"></a>   
## ByRef Variant 마샬링  
 variant 자체는 값으로 전달될 수도 있고 참조로 전달될 수도 있지만, **VT\_BYREF** 플래그를 variant 형식과 함께 사용하여 variant의 내용이 값 대신 참조로 전달됨을 나타낼 수도 있습니다.  variant를 참조로 마샬링하는 것과 **VT\_BYREF** 플래그를 설정한 상태에서 variant를 마샬링하는 것 사이의 차이는 혼란스러울 수 있습니다.  다음 그림에서는 이러한 차이를 명확하게 보여 줍니다.  
  
 ![스택에 전달되는 Variant](../../../docs/framework/interop/media/interopvariant.gif "interopvariant")  
값 및 참조로 전달되는 Variant  
  
 **개체 및 variant를 값으로 마샬링하는 기본 동작**  
  
-   개체를 관리 코드에서 COM으로 전달할 때 개체의 내용은 [개체를 Variant로 마샬링](#cpcondefaultmarshalingforobjectsanchor3)에 정의된 규칙을 사용하여 마샬러에서 만든 새 variant로 복사됩니다.  관리되지 않는 쪽에서 variant에 대해 변경한 내용은 호출에서 반환될 때 원래 개체로 다시 전파되지 않습니다.  
  
-   variant를 COM에서 관리 코드로 복사할 때 variant의 내용은 [Variant를 개체로 마샬링](#cpcondefaultmarshalingforobjectsanchor4)에 정의된 규칙을 사용하여 새로 만든 개체로 복사됩니다.  관리되는 쪽에서 개체에 대해 변경한 내용은 호출에서 반환될 때 원래 variant로 다시 전파되지 않습니다.  
  
 **개체 및 variant를 참조로 마샬링하는 기본 동작**  
  
 변경 내용을 호출자에게 다시 전파하려면 매개 변수를 참조로 전달해야 합니다.  예를 들어, C\#에서는 **ref** 키워드를 사용하고 Visual Basic의 관리 코드에서는 **ByRef**를 사용하여 매개 변수를 참조로 전달할 수 있습니다.  COM에서는 **variant \*** 등의 포인터를 사용하여 참조 매개 변수가 전달됩니다.  
  
-   개체를 참조로 COM에 전달할 때 마샬러에서는 새 variant를 만들고 호출이 실행되기 전에 해당 개체 참조의 내용을 이 variant로 복사합니다.  이 variant는 사용자가 variant의 내용을 자유롭게 변경할 수 있는 관리되지 않는 함수에 전달됩니다.  호출에서 반환될 때, 관리되지 않는 쪽에서 variant에 대해 변경한 내용은 원래 개체로 다시 전파됩니다.  variant의 형식이 호출할 때 전달된 variant의 형식과 다른 경우에는 변경된 내용이 다른 형식의 개체에 다시 전파됩니다.  즉, 호출할 때 전달된 개체의 형식은 호출에서 반환된 개체의 형식과 다를 수 있습니다.  
  
-   variant를 관리 코드에 참조로 전달할 때 마샬러에서는 새 개체를 만들고 호출이 실행되기 전에 해당 variant의 내용을 이 개체로 복사합니다.  개체에 대한 참조는 사용자가 개체를 자유롭게 변경할 수 있는 관리되는 함수에 전달됩니다.  호출에서 반환될 때, 참조되는 개체에 대해 변경한 내용은 원래 variant로 다시 전파됩니다.  개체의 형식이 호출할 때 전달된 개체의 형식과 다른 경우에는 원래 variant의 형식이 변경되고 해당 값이 다시 variant로 전파됩니다.  즉, 호출할 때 전달된 variant의 형식은 호출에서 반환된 variant의 형식과 다를 수 있습니다.  
  
 **VT\_BYREF 플래그를 설정한 상태에서 variant를 마샬링하는 기본 동작**  
  
-   관리 코드에 값으로 전달되는 variant에는 해당 variant에 값 대신 참조가 포함되어 있음을 나타내기 위해 설정된 **VT\_BYREF** 플래그가 있을 수 있습니다.  이 경우 해당 variant는 값으로 전달되기 때문에 여전히 개체로 마샬링됩니다.  마샬러에서는 자동으로 variant의 내용을 역참조하고 호출이 실행되기 전에 이를 새로 만든 개체로 복사합니다.  그런 다음에는 이 개체가 관리되는 함수에 전달되지만, 호출에서 반환될 때는 개체가 원래 variant로 다시 전파되지 않습니다.  관리되는 개체에 대해 변경한 내용은 잃게 됩니다.  
  
    > [!CAUTION]
    >  값으로 전달되는 variant는 **VT\_BYREF** 플래그가 설정된 경우에도 variant의 값을 변경할 수 없습니다.  
  
-   관리 코드에 참조로 전달되는 variant에도 해당 variant에 다른 참조가 포함되어 있음을 나타내기 위해 설정된 **VT\_BYREF** 플래그가 있을 수 있습니다.  이 경우 해당 variant는 참조로 전달되기 때문에 **ref** 개체로 마샬링됩니다.  마샬러에서는 자동으로 variant의 내용을 역참조하고 호출이 실행되기 전에 이를 새로 만든 개체로 복사합니다.  호출에서 반환될 때 개체의 값은 해당 개체가 전달된 개체와 동일한 형식인 경우에만 다시 원래 variant 내의 참조로 전파됩니다.  즉, **VT\_BYREF** 플래그가 설정된 상태에서는 전파할 때 variant의 형식이 변경되지 않습니다.  개체 형식이 호출하는 동안 변경된 경우에는 호출에서 반환될 때 <xref:System.InvalidCastException>이 발생합니다.  
  
 다음 표에서는 variant 및 개체의 전파 규칙을 간단히 보여 줍니다.  
  
|From|To|다시 전파되는 변경 내용|  
|----------|--------|-------------------|  
|**Variant**  *v*|**개체**  *o*|절대 지원되지 않음|  
|**개체**  *o*|**Variant**  *v*|절대 지원되지 않음|  
|**Variant**   ***\****  *pv*|**Ref 개체**  *o*|항상|  
|**Ref 개체**  *o*|**Variant**   ***\****  *pv*|항상|  
|**Variant**  *v* **\(VT\_BYREF** *&#124;*  **VT\_\*\)**|**개체**  *o*|절대 지원되지 않음|  
|**Variant**  *v* **\(VT\_BYREF** *&#124;*  **VT\_\)**|**Ref 개체**  *o*|형식이 변경되지 않은 경우에만|  
  
## 참고 항목  
 [기본 마샬링 동작](../../../docs/framework/interop/default-marshaling-behavior.md)   
 [Blittable 형식 및 비 Blittable 형식](../../../docs/framework/interop/blittable-and-non-blittable-types.md)   
 [Directional Attributes](http://msdn.microsoft.com/ko-kr/241ac5b5-928e-4969-8f58-1dbc048f9ea2)   
 [복사 및 고정](../../../docs/framework/interop/copying-and-pinning.md)