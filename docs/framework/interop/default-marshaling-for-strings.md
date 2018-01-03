---
title: "문자열에 대한 기본 마샬링"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings, interop marshaling
- interop marshaling, strings
ms.assetid: 9baea3ce-27b3-4b4f-af98-9ad0f9467e6f
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8f8de04f9674e67bf1498fb8f25f2b3c61fec438
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="default-marshaling-for-strings"></a><span data-ttu-id="6c9ee-102">문자열에 대한 기본 마샬링</span><span class="sxs-lookup"><span data-stu-id="6c9ee-102">Default Marshaling for Strings</span></span>
<span data-ttu-id="6c9ee-103"><xref:System.String?displayProperty=nameWithType> 및 <xref:System.Text.StringBuilder?displayProperty=nameWithType> 클래스는 마샬링 동작이 서로 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-103">Both the <xref:System.String?displayProperty=nameWithType> and <xref:System.Text.StringBuilder?displayProperty=nameWithType> classes have similar marshaling behavior.</span></span>  
  
 <span data-ttu-id="6c9ee-104">문자열은 COM 스타일 `BSTR` 형식 또는 null로 끝나는 문자열(null 문자로 끝나는 문자 배열)로 마샬링됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-104">Strings are marshaled as a COM-style `BSTR` type or as a null-terminated string (a character array that ends with a null character).</span></span> <span data-ttu-id="6c9ee-105">문자열 내의 문자는 유니코드(Windows 시스템에서 기본값) 또는 ANSI로 마샬링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-105">The characters within the string can be marshaled as Unicode (the default on Windows systems) or ANSI.</span></span>  
  
 <span data-ttu-id="6c9ee-106">이 항목에서는 문자열 형식 마샬링에 대한 다음 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-106">This topic provides the following information on marshaling string types:</span></span>  
  
-   [<span data-ttu-id="6c9ee-107">인터페이스에서 사용되는 문자열</span><span class="sxs-lookup"><span data-stu-id="6c9ee-107">Strings Used in Interfaces</span></span>](#cpcondefaultmarshalingforstringsanchor1)  
  
-   [<span data-ttu-id="6c9ee-108">플랫폼 호출에서 사용되는 문자열</span><span class="sxs-lookup"><span data-stu-id="6c9ee-108">Strings Used in Platform Invoke</span></span>](#cpcondefaultmarshalingforstringsanchor5)  
  
-   [<span data-ttu-id="6c9ee-109">구조체에서 사용되는 문자열</span><span class="sxs-lookup"><span data-stu-id="6c9ee-109">Strings Used in Structures</span></span>](#cpcondefaultmarshalingforstringsanchor2)  
  
-   [<span data-ttu-id="6c9ee-110">고정 길이 문자열 버퍼</span><span class="sxs-lookup"><span data-stu-id="6c9ee-110">Fixed-Length String Buffers</span></span>](#cpcondefaultmarshalingforstringsanchor3)  
  
<a name="cpcondefaultmarshalingforstringsanchor1"></a>   
## <a name="strings-used-in-interfaces"></a><span data-ttu-id="6c9ee-111">인터페이스에서 사용되는 문자열</span><span class="sxs-lookup"><span data-stu-id="6c9ee-111">Strings Used in Interfaces</span></span>  
 <span data-ttu-id="6c9ee-112">다음 표에서는 비관리 코드에 대한 메서드 인수로 마샬링하는 경우 문자열 데이터 형식에 대한 마샬링 옵션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-112">The following table shows the marshaling options for the string data type when marshaled as a method argument to unmanaged code.</span></span> <span data-ttu-id="6c9ee-113"><xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성은 문자열을 COM 인터페이스로 마샬링하기 위한 여러 <xref:System.Runtime.InteropServices.UnmanagedType> 열거형 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-113">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal strings to COM interfaces.</span></span>  
  
|<span data-ttu-id="6c9ee-114">열거형 형식</span><span class="sxs-lookup"><span data-stu-id="6c9ee-114">Enumeration type</span></span>|<span data-ttu-id="6c9ee-115">관리되지 않는 형식에 대한 설명</span><span class="sxs-lookup"><span data-stu-id="6c9ee-115">Description of unmanaged format</span></span>|  
|----------------------|-------------------------------------|  
|<span data-ttu-id="6c9ee-116">`UnmanagedType.BStr`(기본값)</span><span class="sxs-lookup"><span data-stu-id="6c9ee-116">`UnmanagedType.BStr` (default)</span></span>|<span data-ttu-id="6c9ee-117">고정 길이 및 유니코드 문자를 가진 COM 스타일 `BSTR`입니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-117">A COM-style `BSTR` with a prefixed length and Unicode characters.</span></span>|  
|`UnmanagedType.LPStr`|<span data-ttu-id="6c9ee-118">null로 끝나는 ANSI 문자 배열에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-118">A pointer to a null-terminated array of ANSI characters.</span></span>|  
|`UnmanagedType.LPWStr`|<span data-ttu-id="6c9ee-119">null로 끝나는 유니코드 문자 배열에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-119">A pointer to a null-terminated array of Unicode characters.</span></span>|  
  
 <span data-ttu-id="6c9ee-120">이 표는 문자열에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-120">This table applies to strings.</span></span> <span data-ttu-id="6c9ee-121">그러나 <xref:System.Text.StringBuilder>에 사용할 수 있는 옵션은 `UnmanagedType.LPStr` 및 `UnmanagedType.LPWStr`뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-121">However, for <xref:System.Text.StringBuilder>, the only options allowed are `UnmanagedType.LPStr` and `UnmanagedType.LPWStr`.</span></span>  
  
 <span data-ttu-id="6c9ee-122">다음 예제에서는 `IStringWorker` 인터페이스에서 선언된 문자열을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-122">The following example shows strings declared in the `IStringWorker` interface.</span></span>  
  
```cpp  
public interface IStringWorker {  
void PassString1(String s);  
void PassString2([MarshalAs(UnmanagedType.BStr)]String s);  
void PassString3([MarshalAs(UnmanagedType.LPStr)]String s);  
void PassString4([MarshalAs(UnmanagedType.LPWStr)]String s);  
void PassStringRef1(ref String s);  
void PassStringRef2([MarshalAs(UnmanagedType.BStr)]ref String s);  
void PassStringRef3([MarshalAs(UnmanagedType.LPStr)]ref String s);  
void PassStringRef4([MarshalAs(UnmanagedType.LPWStr)]ref String s);  
);  
```  
  
 <span data-ttu-id="6c9ee-123">다음 예제에서는 형식 라이브러리에서 설명된 해당 인터페이스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-123">The following example shows the corresponding interface described in a type library.</span></span>  
  
```  
[…]  
interface IStringWorker : IDispatch {  
HRESULT PassString1([in] BSTR s);  
HRESULT PassString2([in] BSTR s);  
HRESULT PassString3([in] LPStr s);  
HRESULT PassString4([in] LPWStr s);  
HRESULT PassStringRef1([in, out] BSTR *s);  
HRESULT PassStringRef2([in, out] BSTR *s);  
HRESULT PassStringRef3([in, out] LPStr *s);  
HRESULT PassStringRef4([in, out] LPWStr *s);  
);  
```  
  
<a name="cpcondefaultmarshalingforstringsanchor5"></a>   
## <a name="strings-used-in-platform-invoke"></a><span data-ttu-id="6c9ee-124">플랫폼 호출에서 사용되는 문자열</span><span class="sxs-lookup"><span data-stu-id="6c9ee-124">Strings Used in Platform Invoke</span></span>  
 <span data-ttu-id="6c9ee-125">플랫폼 호출은 문자열 인수를 복사하고 .NET Framework 형식(유니코드)을 플랫폼 관리되지 않는 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-125">Platform invoke copies string arguments, converting from the .NET Framework format (Unicode) to the platform unmanaged format.</span></span> <span data-ttu-id="6c9ee-126">문자열을 변경할 수 없으며, 호출이 반환될 때 관리되지 않는 메모리에서 관리되는 메모리로 다시 복사되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-126">Strings are immutable and are not copied back from unmanaged memory to managed memory when the call returns.</span></span>  
  
 <span data-ttu-id="6c9ee-127">다음 표에서는 플랫폼 호출의 메서드 인수로 마샬링하는 경우 문자열에 대한 마샬링 옵션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-127">The following table lists the marshaling options for strings when marshaled as a method argument of a platform invoke call.</span></span> <span data-ttu-id="6c9ee-128"><xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성은 문자열을 마샬링하기 위한 여러 <xref:System.Runtime.InteropServices.UnmanagedType> 열거형 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-128">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal strings.</span></span>  
  
|<span data-ttu-id="6c9ee-129">열거형 형식</span><span class="sxs-lookup"><span data-stu-id="6c9ee-129">Enumeration type</span></span>|<span data-ttu-id="6c9ee-130">관리되지 않는 형식에 대한 설명</span><span class="sxs-lookup"><span data-stu-id="6c9ee-130">Description of unmanaged format</span></span>|  
|----------------------|-------------------------------------|  
|`UnmanagedType.AnsiBStr`|<span data-ttu-id="6c9ee-131">고정 길이 및 ANSI 문자를 가진 COM 스타일 `BSTR`입니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-131">A COM-style `BSTR` with a prefixed length and ANSI characters.</span></span>|  
|`UnmanagedType.BStr`|<span data-ttu-id="6c9ee-132">고정 길이 및 유니코드 문자를 가진 COM 스타일 `BSTR`입니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-132">A COM-style `BSTR` with a prefixed length and Unicode characters.</span></span>|  
|`UnmanagedType.LPStr`|<span data-ttu-id="6c9ee-133">null로 끝나는 ANSI 문자 배열에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-133">A pointer to a null-terminated array of ANSI characters.</span></span>|  
|`UnmanagedType.LPTStr`|<span data-ttu-id="6c9ee-134">null로 끝나는 플랫폼 종속 문자 배열에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-134">A pointer to a null-terminated array of platform-dependent characters.</span></span>|  
|`UnmanagedType.LPWStr`|<span data-ttu-id="6c9ee-135">null로 끝나는 유니코드 문자 배열에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-135">A pointer to a null-terminated array of Unicode characters.</span></span>|  
|`UnmanagedType.TBStr`|<span data-ttu-id="6c9ee-136">고정 길이 및 플랫폼 종속 문자를 가진 COM 스타일 `BSTR`입니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-136">A COM-style `BSTR` with a prefixed length and platform-dependent characters.</span></span>|  
|`VBByRefStr`|<span data-ttu-id="6c9ee-137">Visual Basic .NET에서 비관리 코드의 문자열을 변경하고 결과를 관리 코드에 반영되도록 하는 데 사용할 수 있는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-137">A value that enables Visual Basic .NET to change a string in unmanaged code, and have the results reflected in managed code.</span></span> <span data-ttu-id="6c9ee-138">이 값은 플랫폼 호출에만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-138">This value is supported only for platform invoke.</span></span> <span data-ttu-id="6c9ee-139">Visual Basic의 `ByVal` 문자열에 대한 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-139">This is default value in Visual Basic for `ByVal` strings.</span></span>|  
  
 <span data-ttu-id="6c9ee-140">이 표는 문자열에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-140">This table applies to strings.</span></span> <span data-ttu-id="6c9ee-141">그러나 <xref:System.Text.StringBuilder>에 사용할 수 있는 옵션은 `LPStr`, `LPTStr` 및 `LPWStr`뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-141">However, for <xref:System.Text.StringBuilder>, the only options allowed are `LPStr`, `LPTStr`, and `LPWStr`.</span></span>  
  
 <span data-ttu-id="6c9ee-142">다음 형식 정의는 플랫폼 호출에 대한 `MarshalAsAttribute`의 올바른 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-142">The following type definition shows the correct use of `MarshalAsAttribute` for platform invoke calls.</span></span>  
  
```vb  
Class StringLibAPI      
Public Declare Auto Sub PassLPStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.LPStr)> s As String)      
Public Declare Auto Sub PassLPWStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.LPWStr)> s As String)      
Public Declare Auto Sub PassLPTStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.LPTStr)> s As String)      
Public Declare Auto Sub PassBStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.BStr)> s As String)      
Public Declare Auto Sub PassAnsiBStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.AnsiBStr)> s As String)      
Public Declare Auto Sub PassTBStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.TBStr)> s As String)  
End Class  
```  
  
```csharp  
class StringLibAPI {  
[DllImport("StringLib.Dll")]  
public static extern void PassLPStr([MarshalAs(UnmanagedType.LPStr)]  
String s);  
[DllImport("StringLib.Dll")]  
public static extern void   
PassLPWStr([MarshalAs(UnmanagedType.LPWStr)]String s);  
[DllImport("StringLib.Dll")]  
public static extern void   
PassLPTStr([MarshalAs(UnmanagedType.LPTStr)]String s);  
[DllImport("StringLib.Dll")]  
public static extern void PassBStr([MarshalAs(UnmanagedType.BStr)]  
String s);  
[DllImport("StringLib.Dll")]  
public static extern void   
PassAnsiBStr([MarshalAs(UnmanagedType.AnsiBStr)]String s);  
[DllImport("StringLib.Dll")]  
public static extern void PassTBStr([MarshalAs(UnmanagedType.TBStr)]  
String s);  
}  
```  
  
<a name="cpcondefaultmarshalingforstringsanchor2"></a>   
## <a name="strings-used-in-structures"></a><span data-ttu-id="6c9ee-143">구조체에서 사용되는 문자열</span><span class="sxs-lookup"><span data-stu-id="6c9ee-143">Strings Used in Structures</span></span>  
 <span data-ttu-id="6c9ee-144">문자열은 구조체의 유효한 멤버지만 <xref:System.Text.StringBuilder> 버퍼는 구조체에서 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-144">Strings are valid members of structures; however, <xref:System.Text.StringBuilder> buffers are invalid in structures.</span></span> <span data-ttu-id="6c9ee-145">다음 표에서는 형식을 필드로 마샬링하는 경우 문자열 데이터 형식에 대한 마샬링 옵션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-145">The following table shows the marshaling options for the string data type when the type is marshaled as a field.</span></span> <span data-ttu-id="6c9ee-146"><xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성은 문자열을 필드로 마샬링하기 위한 여러 <xref:System.Runtime.InteropServices.UnmanagedType> 열거형 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-146">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal strings to a field.</span></span>  
  
|<span data-ttu-id="6c9ee-147">열거형 형식</span><span class="sxs-lookup"><span data-stu-id="6c9ee-147">Enumeration type</span></span>|<span data-ttu-id="6c9ee-148">관리되지 않는 형식에 대한 설명</span><span class="sxs-lookup"><span data-stu-id="6c9ee-148">Description of unmanaged format</span></span>|  
|----------------------|-------------------------------------|  
|`UnmanagedType.BStr`|<span data-ttu-id="6c9ee-149">고정 길이 및 유니코드 문자를 가진 COM 스타일 `BSTR`입니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-149">A COM-style `BSTR` with a prefixed length and Unicode characters.</span></span>|  
|`UnmanagedType.LPStr`|<span data-ttu-id="6c9ee-150">null로 끝나는 ANSI 문자 배열에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-150">A pointer to a null-terminated array of ANSI characters.</span></span>|  
|`UnmanagedType.LPTStr`|<span data-ttu-id="6c9ee-151">null로 끝나는 플랫폼 종속 문자 배열에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-151">A pointer to a null-terminated array of platform-dependent characters.</span></span>|  
|`UnmanagedType.LPWStr`|<span data-ttu-id="6c9ee-152">null로 끝나는 유니코드 문자 배열에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-152">A pointer to a null-terminated array of Unicode characters.</span></span>|  
|`UnmanagedType.ByValTStr`|<span data-ttu-id="6c9ee-153">고정 길이 문자 배열입니다. 배열 형식은 포함하는 구조체의 문자 집합에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-153">A fixed-length array of characters; the array's type is determined by the character set of the containing structure.</span></span>|  
  
 <span data-ttu-id="6c9ee-154">`ByValTStr` 형식은 구조체 내에 나타나는 인라인 고정 길이 문자 배열에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-154">The `ByValTStr` type is used for inline, fixed-length character arrays that appear within a structure.</span></span> <span data-ttu-id="6c9ee-155">다른 형식은 문자열에 대한 포인터를 포함하는 구조체 내에 포함된 문자열 참조에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-155">Other types apply to string references contained within structures that contain pointers to strings.</span></span>  
  
 <span data-ttu-id="6c9ee-156">포함하는 구조체에 적용된 <xref:System.Runtime.InteropServices.StructLayoutAttribute> 특성의 `CharSet` 인수는 구조체에서 문자열의 문자 형식을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-156">The `CharSet` argument of the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute that is applied to the containing structure determines the character format of strings in structures.</span></span> <span data-ttu-id="6c9ee-157">다음 구조체 예에서는 문자열 참조 및 인라인 문자열뿐 아니라 ANSI, 유니코드 및 플랫폼 종속 문자를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-157">The following example structures contain string references and inline strings, as well as ANSI, Unicode, and platform-dependent characters.</span></span>  
  
### <a name="type-library-representation"></a><span data-ttu-id="6c9ee-158">형식 라이브러리 표현</span><span class="sxs-lookup"><span data-stu-id="6c9ee-158">Type Library Representation</span></span>  
  
```  
struct StringInfoA {  
   char *    f1;  
   char      f2[256];  
};  
struct StringInfoW {  
   WCHAR *   f1;  
   WCHAR     f2[256];  
   BSTR      f3;  
};  
struct StringInfoT {  
   TCHAR *   f1;  
   TCHAR     f2[256];  
};  
```  
  
 <span data-ttu-id="6c9ee-159">다음 코드 예제에서는 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성을 사용하여 동일한 구조체를 다양한 형식으로 정의하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-159">The following code example shows how to use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to define the same structure in different formats.</span></span>  
  
```vb  
<StructLayout(LayoutKind.Sequential, CharSet := CharSet.Ansi)> _  
Structure StringInfoA  
<MarshalAs(UnmanagedType.LPStr)> Public f1 As String  
<MarshalAs(UnmanagedType.ByValTStr, SizeConst := 256)> _  
Public f2 As String  
End Structure  
<StructLayout(LayoutKind.Sequential, CharSet := CharSet.Unicode)> _  
Structure StringInfoW  
<MarshalAs(UnmanagedType.LPWStr)> Public f1 As String  
<MarshalAs(UnmanagedType.ByValTStr, SizeConst := 256)> _  
Public f2 As String  
<MarshalAs(UnmanagedType.BStr)> Public f3 As String  
End Structure  
<StructLayout(LayoutKind.Sequential, CharSet := CharSet.Auto)> _  
Structure StringInfoT  
<MarshalAs(UnmanagedType.LPTStr)> Public f1 As String  
<MarshalAs(UnmanagedType.ByValTStr, SizeConst := 256)> _  
Public f2 As String  
End Structure  
```  
  
```csharp  
[StructLayout(LayoutKind.Sequential, CharSet=CharSet.Ansi)]  
struct StringInfoA {  
   [MarshalAs(UnmanagedType.LPStr)] public String f1;  
   [MarshalAs(UnmanagedType.ByValTStr, SizeConst=256)] public String f2;  
}  
[StructLayout(LayoutKind.Sequential, CharSet=CharSet.Unicode)]  
struct StringInfoW {  
   [MarshalAs(UnmanagedType.LPWStr)] public String f1;  
   [MarshalAs(UnmanagedType.ByValTStr, SizeConst=256)] public String f2;  
   [MarshalAs(UnmanagedType.BStr)] public String f3;  
}  
[StructLayout(LayoutKind.Sequential, CharSet=CharSet.Auto)]  
struct StringInfoT {  
   [MarshalAs(UnmanagedType.LPTStr)] public String f1;  
   [MarshalAs(UnmanagedType.ByValTStr, SizeConst=256)] public String f2;  
}  
```  
  
<a name="cpcondefaultmarshalingforstringsanchor3"></a>   
## <a name="fixed-length-string-buffers"></a><span data-ttu-id="6c9ee-160">고정 길이 문자열 버퍼</span><span class="sxs-lookup"><span data-stu-id="6c9ee-160">Fixed-Length String Buffers</span></span>  
 <span data-ttu-id="6c9ee-161">일부 환경에서는 고정 길이 문자 버퍼를 조작할 비관리 코드로 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-161">In some circumstances, a fixed-length character buffer must be passed into unmanaged code to be manipulated.</span></span> <span data-ttu-id="6c9ee-162">호출 수신자는 전달된 버퍼의 내용을 수정할 수 없기 때문에 이 경우 단순히 문자열을 전달하면 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-162">Simply passing a string does not work in this case because the callee cannot modify the contents of the passed buffer.</span></span> <span data-ttu-id="6c9ee-163">문자열이 참조로 전달되는 경우 버퍼를 지정된 크기로 초기화할 수 있는 방법이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-163">Even if the string is passed by reference, there is no way to initialize the buffer to a given size.</span></span>  
  
 <span data-ttu-id="6c9ee-164">솔루션은 문자열 대신 <xref:System.Text.StringBuilder> 버퍼를 인수로 전달하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-164">The solution is to pass a <xref:System.Text.StringBuilder> buffer as the argument instead of a string.</span></span> <span data-ttu-id="6c9ee-165">`StringBuilder`의 용량을 초과하지 않는 한 호출 수신자가 `StringBuilder`를 역참조 및 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-165">A `StringBuilder` can be dereferenced and modified by the callee, provided it does not exceed the capacity of the `StringBuilder`.</span></span> <span data-ttu-id="6c9ee-166">고정 길이로 초기화할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-166">It can also be initialized to a fixed length.</span></span> <span data-ttu-id="6c9ee-167">예를 들어 `StringBuilder` 버퍼를 `N` 용량으로 초기화하는 경우 마샬러가 (`N`+1)자 크기의 버퍼를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-167">For example, if you initialize a `StringBuilder` buffer to a capacity of `N`, the marshaler provides a buffer of size (`N`+1) characters.</span></span> <span data-ttu-id="6c9ee-168">+1은 `StringBuilder`에는 없는데 관리되지 않는 문자열에 null 종결자가 있다는 사실을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-168">The +1 accounts for the fact that the unmanaged string has a null terminator while `StringBuilder` does not.</span></span>  
  
 <span data-ttu-id="6c9ee-169">예를 들어 Microsoft Win32 API `GetWindowText` 함수(Windows.h에서 정의됨)는 조작할 비관리 코드에 전달해야 하는 고정 길이 문자 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-169">For example, the Microsoft Win32 API `GetWindowText` function (defined in Windows.h) is a fixed-length character buffer that must be passed into unmanaged code to be manipulated.</span></span> <span data-ttu-id="6c9ee-170">`LpString`은 크기가 `nMaxCount`인 호출자 할당 버퍼를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-170">`LpString` points to a caller-allocated buffer of size `nMaxCount`.</span></span> <span data-ttu-id="6c9ee-171">호출자는 버퍼를 할당하고 `nMaxCount` 인수를 할당된 버퍼 크기로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-171">The caller is expected to allocate the buffer and set the `nMaxCount` argument to the size of the allocated buffer.</span></span> <span data-ttu-id="6c9ee-172">다음 코드에서는 Windows.h에서 정의된 `GetWindowText` 함수 선언을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-172">The following code shows the `GetWindowText` function declaration as defined in Windows.h.</span></span>  
  
```  
int GetWindowText(  
HWND hWnd,        // Handle to window or control.  
LPTStr lpString,  // Text buffer.  
int nMaxCount     // Maximum number of characters to copy.  
);  
```  
  
 <span data-ttu-id="6c9ee-173">`StringBuilder`의 용량을 초과하지 않는 한 호출 수신자가 `StringBuilder`를 역참조 및 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-173">A `StringBuilder` can be dereferenced and modified by the callee, provided it does not exceed the capacity of the `StringBuilder`.</span></span> <span data-ttu-id="6c9ee-174">다음 코드 예제에서는 `StringBuilder`를 고정 길이로 초기화할 수 있는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6c9ee-174">The following code example demonstrates how `StringBuilder` can be initialized to a fixed length.</span></span>  
  
```vb  
Public Class Win32API  
Public Declare Auto Sub GetWindowText Lib "User32.Dll" _  
(h As Integer, s As StringBuilder, nMaxCount As Integer)  
End Class  
Public Class Window  
   Friend h As Integer ' Friend handle to Window.  
   Public Function GetText() As String  
      Dim sb As New StringBuilder(256)  
      Win32API.GetWindowText(h, sb, sb.Capacity + 1)  
   Return sb.ToString()  
   End Function  
End Class  
```  
  
```csharp  
public class Win32API {  
[DllImport("User32.Dll")]  
public static extern void GetWindowText(int h, StringBuilder s,   
int nMaxCount);  
}  
public class Window {  
   internal int h;        // Internal handle to Window.  
   public String GetText() {  
      StringBuilder sb = new StringBuilder(256);  
      Win32API.GetWindowText(h, sb, sb.Capacity + 1);  
   return sb.ToString();  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="6c9ee-175">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6c9ee-175">See Also</span></span>  
 [<span data-ttu-id="6c9ee-176">기본 마샬링 동작</span><span class="sxs-lookup"><span data-stu-id="6c9ee-176">Default Marshaling Behavior</span></span>](../../../docs/framework/interop/default-marshaling-behavior.md)  
 [<span data-ttu-id="6c9ee-177">Blittable 형식 및 비 Blittable 형식</span><span class="sxs-lookup"><span data-stu-id="6c9ee-177">Blittable and Non-Blittable Types</span></span>](../../../docs/framework/interop/blittable-and-non-blittable-types.md)  
 [<span data-ttu-id="6c9ee-178">방향 특성</span><span class="sxs-lookup"><span data-stu-id="6c9ee-178">Directional Attributes</span></span>](http://msdn.microsoft.com/en-us/241ac5b5-928e-4969-8f58-1dbc048f9ea2)  
 [<span data-ttu-id="6c9ee-179">복사 및 고정</span><span class="sxs-lookup"><span data-stu-id="6c9ee-179">Copying and Pinning</span></span>](../../../docs/framework/interop/copying-and-pinning.md)
