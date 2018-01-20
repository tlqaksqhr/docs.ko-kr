---
title: "관리 코드에서 프로토타입 만들기"
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
- cpp
helpviewer_keywords:
- prototypes in managed code
- COM interop, DLL functions
- unmanaged functions
- platform invoke, creating prototypes
- COM interop, platform invoke
- interoperation with unmanaged code, DLL functions
- interoperation with unmanaged code, platform invoke
- platform invoke, object fields
- DLL functions
- object fields in platform invoke
ms.assetid: ecdcf25d-cae3-4f07-a2b6-8397ac6dc42d
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d1006f59f9841a10066c83a8f0800d3a7c17500a
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="creating-prototypes-in-managed-code"></a><span data-ttu-id="c5404-102">관리 코드에서 프로토타입 만들기</span><span class="sxs-lookup"><span data-stu-id="c5404-102">Creating Prototypes in Managed Code</span></span>
<span data-ttu-id="c5404-103">이 항목에서는 관리되지 않는 함수에 액세스하는 방법을 설명하고 관리 코드에서 메서드 정의에 주석을 다는 여러 특성 필드를 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="c5404-103">This topic describes how to access unmanaged functions and introduces several attribute fields that annotate method definition in managed code.</span></span> <span data-ttu-id="c5404-104">플랫폼 호출에서 사용되는 .NET 기반 선언을 생성하는 방법을 보여 주는 예제는 [플랫폼 호출을 사용하여 데이터 마샬링](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5404-104">For examples that demonstrate how to construct .NET-based declarations to be used with platform invoke, see [Marshaling Data with Platform Invoke](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md).</span></span>  
  
 <span data-ttu-id="c5404-105">관리 코드에서 관리되지 않는 DLL 함수에 액세스하기 전에 함수 이름과 함수를 내보내는 DLL 이름을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5404-105">Before you can access an unmanaged DLL function from managed code, you need to know the name of the function and the name of the DLL that exports it.</span></span> <span data-ttu-id="c5404-106">이 정보를 사용하여 DLL에서 구현되는 관리되지 않는 함수에 대한 관리되는 정의를 쓰기 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5404-106">With this information, you can begin to write the managed definition for an unmanaged function that is implemented in a DLL.</span></span> <span data-ttu-id="c5404-107">또한 플랫폼 호출이 함수를 만들고 데이터를 함수로 또는 반대로 마샬링하는 방법을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5404-107">Furthermore, you can adjust the way that platform invoke creates the function and marshals data to and from the function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c5404-108">문자열을 할당하는 Win32 API 함수를 통해 `LocalFree`와 같은 메서드를 사용하여 문자열을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5404-108">Win32 API functions that allocate a string enable you to free the string by using a method such as `LocalFree`.</span></span> <span data-ttu-id="c5404-109">플랫폼 호출은 매개 변수를 다르게 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="c5404-109">Platform invoke handles such parameters differently.</span></span> <span data-ttu-id="c5404-110">플랫폼 호출의 경우 매개 변수를 `String` 형식 대신 `IntPtr` 형식으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5404-110">For platform invoke calls, make the parameter an `IntPtr` type instead of a `String` type.</span></span> <span data-ttu-id="c5404-111"><xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType> 클래스에서 제공된 메서드를 사용하여 형식을 문자열로 수동으로 변환하고 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="c5404-111">Use methods that are provided by the <xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType> class to convert the type to a string manually and free it manually.</span></span>  
  
## <a name="declaration-basics"></a><span data-ttu-id="c5404-112">선언 기본 사항</span><span class="sxs-lookup"><span data-stu-id="c5404-112">Declaration Basics</span></span>  
 <span data-ttu-id="c5404-113">관리되지 않는 함수에 대한 관리되는 정의는 다음 예제와 같이 언어 종속적입니다.</span><span class="sxs-lookup"><span data-stu-id="c5404-113">Managed definitions to unmanaged functions are language-dependent, as you can see in the following examples.</span></span> <span data-ttu-id="c5404-114">전체 코드 예제를 보려면 [플랫폼 호출 예제](../../../docs/framework/interop/platform-invoke-examples.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5404-114">For more complete code examples, see [Platform Invoke Examples](../../../docs/framework/interop/platform-invoke-examples.md).</span></span>  
  
```vb  
Imports System.Runtime.InteropServices  
Public Class Win32  
    Declare Auto Function MessageBox Lib "user32.dll" _  
       (ByVal hWnd As Integer, _  
        ByVal txt As String, ByVal caption As String, _  
        ByVal Typ As Integer) As IntPtr  
End Class  
```  
  
 <span data-ttu-id="c5404-115"><xref:System.Runtime.InteropServices.DllImportAttribute.BestFitMapping>, <xref:System.Runtime.InteropServices.DllImportAttribute.CallingConvention>, <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling>, <xref:System.Runtime.InteropServices.DllImportAttribute.PreserveSig>, <xref:System.Runtime.InteropServices.DllImportAttribute.SetLastError> 또는 <xref:System.Runtime.InteropServices.DllImportAttribute.ThrowOnUnmappableChar> 필드를 [!INCLUDE[vbprvbext](../../../includes/vbprvbext-md.md)] 선언에 적용하려면 `Declare` 문 대신 <xref:System.Runtime.InteropServices.DllImportAttribute> 특성을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5404-115">To apply the <xref:System.Runtime.InteropServices.DllImportAttribute.BestFitMapping>, <xref:System.Runtime.InteropServices.DllImportAttribute.CallingConvention>, <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling>, <xref:System.Runtime.InteropServices.DllImportAttribute.PreserveSig>, <xref:System.Runtime.InteropServices.DllImportAttribute.SetLastError>, or <xref:System.Runtime.InteropServices.DllImportAttribute.ThrowOnUnmappableChar> fields to a [!INCLUDE[vbprvbext](../../../includes/vbprvbext-md.md)] declaration, you must use the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute instead of the `Declare` statement.</span></span>  
  
```vb  
Imports System.Runtime.InteropServices  
Public Class Win32  
   <DllImport ("user32.dll", CharSet := CharSet.Auto)> _  
   Public Shared Function MessageBox (ByVal hWnd As Integer, _  
        ByVal txt As String, ByVal caption As String, _  
        ByVal Typ As Integer) As IntPtr  
   End Function  
End Class  
```  
  
```csharp  
using System.Runtime.InteropServices;  
[DllImport("user32.dll")]  
    public static extern IntPtr MessageBox(int hWnd, String text,   
                                       String caption, uint type);  
```  
  
```cpp  
using namespace System::Runtime::InteropServices;  
[DllImport("user32.dll")]  
    extern "C" IntPtr MessageBox(int hWnd, String* pText,  
    String* pCaption unsigned int uType);  
```  
  
## <a name="adjusting-the-definition"></a><span data-ttu-id="c5404-116">정의 조정</span><span class="sxs-lookup"><span data-stu-id="c5404-116">Adjusting the Definition</span></span>  
 <span data-ttu-id="c5404-117">명시적으로 설정하는지와 관계없이 특성 필드는 관리 코드 동작을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c5404-117">Whether you set them explicitly or not, attribute fields are at work defining the behavior of managed code.</span></span> <span data-ttu-id="c5404-118">플랫폼 호출은 어셈블리에서 메타데이터로 있는 다양한 필드에 설정된 기본값에 따라 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="c5404-118">Platform invoke operates according to the default values set on various fields that exist as metadata in an assembly.</span></span> <span data-ttu-id="c5404-119">필드 하나 이상의 값을 조정하여 이 기본 동작을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5404-119">You can alter this default behavior by adjusting the values of one or more fields.</span></span> <span data-ttu-id="c5404-120">대부분 <xref:System.Runtime.InteropServices.DllImportAttribute>를 사용하여 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5404-120">In many cases, you use the <xref:System.Runtime.InteropServices.DllImportAttribute> to set a value.</span></span>  
  
 <span data-ttu-id="c5404-121">다음 표에는 플랫폼 호출과 관련된 전체 특성 필드 집합이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5404-121">The following table lists the complete set of attribute fields that pertain to platform invoke.</span></span> <span data-ttu-id="c5404-122">표에는 각 필드에 대한 기본값과 이들 필드를 사용하여 관리되지 않는 DLL 함수를 정의하는 방법에 대한 정보 링크가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5404-122">For each field, the table includes the default value and a link to information on how to use these fields to define unmanaged DLL functions.</span></span>  
  
|<span data-ttu-id="c5404-123">필드</span><span class="sxs-lookup"><span data-stu-id="c5404-123">Field</span></span>|<span data-ttu-id="c5404-124">설명</span><span class="sxs-lookup"><span data-stu-id="c5404-124">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.BestFitMapping>|<span data-ttu-id="c5404-125">최적 매핑을 사용하거나 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5404-125">Enables or disables best-fit mapping.</span></span>|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.CallingConvention>|<span data-ttu-id="c5404-126">메서드 인수 전달 시 사용할 호출 규칙을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5404-126">Specifies the calling convention to use in passing method arguments.</span></span> <span data-ttu-id="c5404-127">기본값은 `WinAPI`로, 32비트 Intel 기반 플랫폼의 `__stdcall`에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="c5404-127">The default is `WinAPI`, which corresponds to `__stdcall` for the 32-bit Intel-based platforms.</span></span>|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.CharSet>|<span data-ttu-id="c5404-128">이름 손상 및 문자열 인수가 함수로 마샬링되는 방법을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="c5404-128">Controls name mangling and the way that string arguments should be marshaled to the function.</span></span> <span data-ttu-id="c5404-129">기본값은 `CharSet.Ansi`입니다.</span><span class="sxs-lookup"><span data-stu-id="c5404-129">The default is `CharSet.Ansi`.</span></span>|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint>|<span data-ttu-id="c5404-130">호출할 DLL 진입점을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5404-130">Specifies the DLL entry point to be called.</span></span>|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling>|<span data-ttu-id="c5404-131">문자 집합과 일치하도록 진입점을 수정해야 하는지를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="c5404-131">Controls whether an entry point should be modified to correspond to the character set.</span></span> <span data-ttu-id="c5404-132">기본값은 프로프래밍 언어에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="c5404-132">The default value varies by programming language.</span></span>|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.PreserveSig>|<span data-ttu-id="c5404-133">HRESULT를 반환하고 반환 값에 대한 추가 [out, retval] 인수가 포함된 관리되지 않는 서명으로 관리되는 메서드 서명을 변환할지를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="c5404-133">Controls whether the managed method signature should be transformed into an unmanaged signature that returns an HRESULT and has an additional [out, retval] argument for the return value.</span></span><br /><br /> <span data-ttu-id="c5404-134">기본값은 `true`입니다(서명을 변환하지 않아야 함).</span><span class="sxs-lookup"><span data-stu-id="c5404-134">The default is `true` (the signature should not be transformed).</span></span>|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.SetLastError>|<span data-ttu-id="c5404-135">호출자가 `Marshal.GetLastWin32Error` API 함수를 사용하여 메서드를 실행하는 동안 오류가 발생했는지를 확인할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5404-135">Enables the caller to use the `Marshal.GetLastWin32Error` API function to determine whether an error occurred while executing the method.</span></span> <span data-ttu-id="c5404-136">Visual Basic에서 기본값은 `true`이고, C# 및 C++에서 기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="c5404-136">In Visual Basic, the default is `true`; in C# and C++, the default is `false`.</span></span>|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.ThrowOnUnmappableChar>|<span data-ttu-id="c5404-137">ANSI "?" 문자로 변환되는 매핑할 수 없는 유니코드 문자에 대한 예외 throw를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="c5404-137">Controls throwing of an exception on an unmappable Unicode character that is converted to an ANSI "?" character.</span></span>|  
  
 <span data-ttu-id="c5404-138">자세한 참조 정보는 <xref:System.Runtime.InteropServices.DllImportAttribute>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5404-138">For detailed reference information, see <xref:System.Runtime.InteropServices.DllImportAttribute>.</span></span>  
  
## <a name="platform-invoke-security-considerations"></a><span data-ttu-id="c5404-139">플랫폼 호출 보안 고려 사항</span><span class="sxs-lookup"><span data-stu-id="c5404-139">Platform invoke security considerations</span></span>  
 <span data-ttu-id="c5404-140"><xref:System.Security.Permissions.SecurityAction> 열거형의 `Assert`, `Deny` 및 `PermitOnly` 멤버를 *스택 워크 한정자*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5404-140">The `Assert`, `Deny`, and `PermitOnly` members of the <xref:System.Security.Permissions.SecurityAction> enumeration are referred to as *stack walk modifiers*.</span></span> <span data-ttu-id="c5404-141">이들 멤버는 플랫폼 호출 선언 및 COM IDL(Interface Definition Language) 문에서 선언 특성으로 사용될 경우 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5404-141">These members are ignored if they are used as declarative attributes on platform invoke declarations and COM Interface Definition Language (IDL) statements.</span></span>  
  
### <a name="platform-invoke-examples"></a><span data-ttu-id="c5404-142">플랫폼 호출 예제</span><span class="sxs-lookup"><span data-stu-id="c5404-142">Platform Invoke Examples</span></span>  
 <span data-ttu-id="c5404-143">이 섹션의 플랫폼 호출 샘플에서는 스택 워크 한정자와 함께 `RegistryPermission` 특성을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c5404-143">The platform invoke samples in this section illustrate the use of the `RegistryPermission` attribute with the stack walk modifiers.</span></span>  
  
 <span data-ttu-id="c5404-144">다음 코드 예제에서는 <xref:System.Security.Permissions.SecurityAction> `Assert`, `Deny`, 및 `PermitOnly` 한정자는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5404-144">In the following code example, the <xref:System.Security.Permissions.SecurityAction>`Assert`, `Deny`, and `PermitOnly` modifiers are ignored.</span></span>  
  
```  
[DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
[RegistryPermission(SecurityAction.Assert, Unrestricted = true)]  
    private static extern bool CallRegistryPermissionAssert();  
  
[DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
[RegistryPermission(SecurityAction.Deny, Unrestricted = true)]  
    private static extern bool CallRegistryPermissionDeny();  
  
[DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
[RegistryPermission(SecurityAction.PermitOnly, Unrestricted = true)]  
    private static extern bool CallRegistryPermissionDeny();  
```  
  
 <span data-ttu-id="c5404-145">그러나 다음 예제에서 `Demand` 한정자는 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5404-145">However, the `Demand` modifier in the following example is accepted.</span></span>  
  
```  
[DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
[RegistryPermission(SecurityAction.Demand, Unrestricted = true)]  
    private static extern bool CallRegistryPermissionDeny();  
```  
  
 <span data-ttu-id="c5404-146"><xref:System.Security.Permissions.SecurityAction> 한정자는 플랫폼 호출을 포함(래핑)하는 클래스에 배치될 경우 제대로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="c5404-146"><xref:System.Security.Permissions.SecurityAction> modifiers do work correctly if they are placed on a class that contains (wraps) the platform invoke call.</span></span>  
  
```cpp  
      [RegistryPermission(SecurityAction.Demand, Unrestricted = true)]  
public ref class PInvokeWrapper  
{  
public:  
[DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
    private static extern bool CallRegistryPermissionDeny();  
};  
```  
  
```csharp  
[RegistryPermission(SecurityAction.Demand, Unrestricted = true)]  
class PInvokeWrapper  
{  
[DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
    private static extern bool CallRegistryPermissionDeny();  
}  
```  
  
 <span data-ttu-id="c5404-147"><xref:System.Security.Permissions.SecurityAction> 한정자는 플랫폼 호출의 호출자에 배치되는 중첩된 시나리오에서도 제대로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="c5404-147"><xref:System.Security.Permissions.SecurityAction> modifiers also work correctly in a nested scenario where they are placed on the caller of the platform invoke call:</span></span>  
  
```cpp  
      {  
public ref class PInvokeWrapper  
public:  
    [DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
    private static extern bool CallRegistryPermissionDeny();  
  
    [RegistryPermission(SecurityAction.Demand, Unrestricted = true)]  
    public static bool CallRegistryPermission()  
    {  
     return CallRegistryPermissionInternal();  
    }  
};  
```  
  
```csharp  
class PInvokeScenario  
{  
    [DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
    private static extern bool CallRegistryPermissionInternal();  
  
    [RegistryPermission(SecurityAction.Assert, Unrestricted = true)]  
    public static bool CallRegistryPermission()  
    {  
     return CallRegistryPermissionInternal();  
    }  
}  
```  
  
#### <a name="com-interop-examples"></a><span data-ttu-id="c5404-148">COM Interop 예제</span><span class="sxs-lookup"><span data-stu-id="c5404-148">COM Interop Examples</span></span>  
 <span data-ttu-id="c5404-149">이 섹션의 COM Interop 샘플에서는 스택 워크 한정자와 함께 `RegistryPermission` 특성을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c5404-149">The COM interop samples in this section illustrate the use of the `RegistryPermission` attribute with the stack walk modifiers.</span></span>  
  
 <span data-ttu-id="c5404-150">이전 섹션의 플랫폼 호출 예제와 비슷하게 다음 COM interop 인터페이스 선언은 `Assert`, `Deny` 및 `PermitOnly` 한정자를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="c5404-150">The following COM interop interface declarations ignore the `Assert`, `Deny`, and `PermitOnly` modifiers, similarly to the platform invoke examples in the previous section.</span></span>  
  
```  
[ComImport, Guid("12345678-43E6-43c9-9A13-47F40B338DE0")]  
interface IAssertStubsItf  
{  
[RegistryPermission(SecurityAction.Assert, Unrestricted = true)]  
    bool CallRegistryPermission();  
[FileIOPermission(SecurityAction.Assert, Unrestricted = true)]  
    bool CallFileIoPermission();  
}  
  
[ComImport, Guid("12345678-43E6-43c9-9A13-47F40B338DE0")]  
interface IDenyStubsItf  
{  
[RegistryPermission(SecurityAction.Deny, Unrestricted = true)]  
    bool CallRegistryPermission();  
[FileIOPermission(SecurityAction.Deny, Unrestricted = true)]  
    bool CallFileIoPermission();  
}  
  
[ComImport, Guid("12345678-43E6-43c9-9A13-47F40B338DE0")]  
interface IAssertStubsItf  
{  
[RegistryPermission(SecurityAction.PermitOnly, Unrestricted = true)]  
    bool CallRegistryPermission();  
[FileIOPermission(SecurityAction.PermitOnly, Unrestricted = true)]  
    bool CallFileIoPermission();  
}  
```  
  
 <span data-ttu-id="c5404-151">또한 다음 예제와 같이 `Demand` 한정자는 COM interop 인터페이스 선언 시나리오에서 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5404-151">Additionally, the `Demand` modifier is not accepted in COM interop interface declaration scenarios, as shown in the following example.</span></span>  
  
```  
[ComImport, Guid("12345678-43E6-43c9-9A13-47F40B338DE0")]  
interface IDemandStubsItf  
{  
[RegistryPermission(SecurityAction.Demand, Unrestricted = true)]  
    bool CallRegistryPermission();  
[FileIOPermission(SecurityAction.Demand, Unrestricted = true)]  
    bool CallFileIoPermission();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="c5404-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c5404-152">See Also</span></span>  
 [<span data-ttu-id="c5404-153">관리되지 않는 DLL 함수 사용</span><span class="sxs-lookup"><span data-stu-id="c5404-153">Consuming Unmanaged DLL Functions</span></span>](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)  
 [<span data-ttu-id="c5404-154">진입점 지정</span><span class="sxs-lookup"><span data-stu-id="c5404-154">Specifying an Entry Point</span></span>](../../../docs/framework/interop/specifying-an-entry-point.md)  
 [<span data-ttu-id="c5404-155">문자 집합 지정</span><span class="sxs-lookup"><span data-stu-id="c5404-155">Specifying a Character Set</span></span>](../../../docs/framework/interop/specifying-a-character-set.md)  
 [<span data-ttu-id="c5404-156">플랫폼 호출 예제</span><span class="sxs-lookup"><span data-stu-id="c5404-156">Platform Invoke Examples</span></span>](../../../docs/framework/interop/platform-invoke-examples.md)  
 [<span data-ttu-id="c5404-157">플랫폼 호출 보안 고려 사항</span><span class="sxs-lookup"><span data-stu-id="c5404-157">Platform Invoke Security Considerations</span></span>](http://msdn.microsoft.com/library/bbcc67f7-50b5-4917-88ed-cb15470409fb)  
 [<span data-ttu-id="c5404-158">DLL 함수 식별</span><span class="sxs-lookup"><span data-stu-id="c5404-158">Identifying Functions in DLLs</span></span>](../../../docs/framework/interop/identifying-functions-in-dlls.md)  
 [<span data-ttu-id="c5404-159">DLL 함수가 포함된 클래스 만들기</span><span class="sxs-lookup"><span data-stu-id="c5404-159">Creating a Class to Hold DLL Functions</span></span>](../../../docs/framework/interop/creating-a-class-to-hold-dll-functions.md)  
 [<span data-ttu-id="c5404-160">DLL 함수 호출</span><span class="sxs-lookup"><span data-stu-id="c5404-160">Calling a DLL Function</span></span>](../../../docs/framework/interop/calling-a-dll-function.md)
