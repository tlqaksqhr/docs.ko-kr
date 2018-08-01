---
title: '방법: CLS 규격이 아닌 예외 catch'
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions [C#], non-CLS
ms.assetid: db4630b3-5240-471a-b3a7-c7ff6ab31e8d
ms.openlocfilehash: c3153da78e0c25d59da7b5d83bd33f8080c7fae8
ms.sourcegitcommit: 2d8b7488d94101b534ca3e9780b1c1e840233405
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2018
ms.locfileid: "39198772"
---
# <a name="how-to-catch-a-non-cls-exception"></a><span data-ttu-id="4b99e-102">방법: CLS 규격이 아닌 예외 catch</span><span class="sxs-lookup"><span data-stu-id="4b99e-102">How to: Catch a non-CLS Exception</span></span>
<span data-ttu-id="4b99e-103">C++/CLI를 포함한 일부 .NET 언어에서는 개체가 <xref:System.Exception>에서 파생되지 않은 예외를 throw할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b99e-103">Some .NET languages, including C++/CLI, allow objects to throw exceptions that do not derive from <xref:System.Exception>.</span></span> <span data-ttu-id="4b99e-104">이러한 예외를 *CLS 규격이 아닌 예외* 또는 *예외가 아닌 항목*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b99e-104">Such exceptions are called *non-CLS exceptions* or *non-Exceptions*.</span></span> <span data-ttu-id="4b99e-105">C#에서는 CLS 규격이 아닌 예외를 throw할 수 없지만 다음 두 가지 방법으로 해당 예외를 catch할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b99e-105">In C# you cannot throw non-CLS exceptions, but you can catch them in two ways:</span></span>  
  
-   <span data-ttu-id="4b99e-106">`catch (RuntimeWrappedException e)` 블록 내에서.</span><span class="sxs-lookup"><span data-stu-id="4b99e-106">Within a `catch (RuntimeWrappedException e)` block.</span></span>
  
     <span data-ttu-id="4b99e-107">기본적으로 Visual C# 어셈블리는 CLS 규격이 아닌 예외를 래핑된 예외로 catch합니다.</span><span class="sxs-lookup"><span data-stu-id="4b99e-107">By default, a Visual C# assembly catches non-CLS exceptions as wrapped exceptions.</span></span> <span data-ttu-id="4b99e-108"><xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> 속성을 통해 액세스할 수 있는 원래 예외에 액세스해야 할 경우 이 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4b99e-108">Use this method if you need access to the original exception, which can be accessed through the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="4b99e-109">이 항목의 뒤에 나오는 절차에서는 이 방식으로 예외를 catch하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4b99e-109">The procedure later in this topic explains how to catch exceptions in this manner.</span></span>  
  
-   <span data-ttu-id="4b99e-110">일반 catch 블록(예외 형식이 지정되지 않은 catch 블록) 내에서 예외는 다른 모든 `catch` 블록 뒤에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b99e-110">Within a general catch block (a catch block without an exception type specified) that is put after all other `catch` blocks.</span></span>
  
     <span data-ttu-id="4b99e-111">CLS 규격이 아닌 예외에 대한 응답으로 일부 작업(예: 로그 파일에 쓰기)을 수행하고자 하고 예외 정보에 액세스할 필요가 없는 경우 이 방법을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4b99e-111">Use this method when you want to perform some action (such as writing to a log file) in response to non-CLS exceptions, and you do not need access to the exception information.</span></span> <span data-ttu-id="4b99e-112">기본적으로 공용 언어 런타임은 모든 예외를 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="4b99e-112">By default the common language runtime wraps all exceptions.</span></span> <span data-ttu-id="4b99e-113">이 동작을 사용하지 않으려면 일반적으로 AssemblyInfo.cs 파일에 있는 어셈블리 수준 특성 `[assembly: RuntimeCompatibilityAttribute(WrapNonExceptionThrows = false)]`를 코드에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4b99e-113">To disable this behavior, add this assembly-level attribute to your code, typically in the AssemblyInfo.cs file: `[assembly: RuntimeCompatibilityAttribute(WrapNonExceptionThrows = false)]`.</span></span>  
  
### <a name="to-catch-a-non-cls-exception"></a><span data-ttu-id="4b99e-114">CLS 규격이 아닌 예외를 catch하려면</span><span class="sxs-lookup"><span data-stu-id="4b99e-114">To catch a non-CLS exception</span></span>  
  
<span data-ttu-id="4b99e-115">`catch(RuntimeWrappedException e)` 블록 내에서 <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> 속성을 통해 원래 예외에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="4b99e-115">Within a `catch(RuntimeWrappedException e)` block, access the original exception through the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b99e-116">예</span><span class="sxs-lookup"><span data-stu-id="4b99e-116">Example</span></span>  
 <span data-ttu-id="4b99e-117">다음 예제에서는 C++/CLI로 작성된 클래스 라이브러리에서 throw된 CLS 규격이 아닌 예외를 catch하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4b99e-117">The following example shows how to catch a non-CLS exception that was thrown from a class library written in C++/CLI.</span></span> <span data-ttu-id="4b99e-118">이 예제에서 C# 클라이언트 코드는 throw되는 예외 형식이 <xref:System.String?displayProperty=nameWithType>이라는 것을 사전에 알고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b99e-118">Note that in this example, the C# client code knows in advance that the exception type being thrown is a <xref:System.String?displayProperty=nameWithType>.</span></span> <span data-ttu-id="4b99e-119">코드에서 해당 형식에 액세스할 수 있으면 <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> 속성을 다시 원래 형식으로 캐스팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b99e-119">You can cast the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> property back its original type as long as that type is accessible from your code.</span></span>  
  
```csharp
// Class library written in C++/CLI.
var myClass = new ThrowNonCLS.Class1();

try
{
    // throws gcnew System::String(  
    // "I do not derive from System.Exception!");  
    myClass.TestThrow();
}
catch (RuntimeWrappedException e)
{
    String s = e.WrappedException as String;
    if (s != null)
    {
        Console.WriteLine(s);
    }
}
```  
  
## <a name="see-also"></a><span data-ttu-id="4b99e-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4b99e-120">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.RuntimeWrappedException>  
 [<span data-ttu-id="4b99e-121">예외 및 예외 처리</span><span class="sxs-lookup"><span data-stu-id="4b99e-121">Exceptions and Exception Handling</span></span>](../../../csharp/programming-guide/exceptions/index.md)
