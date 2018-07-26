---
title: Windows 스토어 앱을 .NET 네이티브로 마이그레이션
ms.date: 03/30/2017
ms.assetid: 4153aa18-6f56-4a0a-865b-d3da743a1d05
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5a44819e8a8c0b07b3ffbfb2d92533cbdc558ef6
ms.sourcegitcommit: 59b51cd7c95c75be85bd6ef715e9ef8c85720bac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37874746"
---
# <a name="migrating-your-windows-store-app-to-net-native"></a><span data-ttu-id="baa43-102">Windows 스토어 앱을 .NET 네이티브로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="baa43-102">Migrating Your Windows Store App to .NET Native</span></span>
<span data-ttu-id="baa43-103">.NET 네이티브 개발자의 컴퓨터 또는 Windows 스토어에서 앱의 정적 컴파일을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-103">.NET Native provides static compilation of apps in the Windows Store or on the developer’s computer.</span></span> <span data-ttu-id="baa43-104">이 기능은 장치의 [네이티브 이미지 생성기(Ngen.exe)](../../../docs/framework/tools/ngen-exe-native-image-generator.md) 또는 JIT(Just-In-Time) 컴파일러가 Windows 스토어 앱에 대해 수행하는 동적 컴파일과는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-104">This differs from the dynamic compilation performed for Windows Store apps by the just-in-time (JIT) compiler or the [Native Image Generator (Ngen.exe)](../../../docs/framework/tools/ngen-exe-native-image-generator.md) on the device.</span></span> <span data-ttu-id="baa43-105">다르기는 하지만.NET 네이티브 호환성을 유지 하려고 사용 하 여 합니다 [Windows 스토어 앱 용.NET](http://msdn.microsoft.com/library/windows/apps/br230302.aspx)합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-105">Despite the differences, .NET Native tries to maintain compatibility with the [.NET for Windows Store apps](http://msdn.microsoft.com/library/windows/apps/br230302.aspx).</span></span> <span data-ttu-id="baa43-106">대부분의 경우.NET 네이티브를 사용 하 여.NET에 대 한 Windows 스토어 앱에서 작동 하는 것도 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-106">For the most part, things that work on the .NET for Windows Store apps also work with .NET Native.</span></span>  <span data-ttu-id="baa43-107">그러나 동작이 변경되는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-107">However, in some cases, you may encounter behavioral changes.</span></span> <span data-ttu-id="baa43-108">이 문서는 다음 영역에서 표준 Windows 스토어 앱 용.NET 및.NET 네이티브 이러한 차이점에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-108">This document discusses these differences between the standard .NET for Windows Store apps and .NET Native in the following areas:</span></span>  
  
-   [<span data-ttu-id="baa43-109">일반 런타임 차이점</span><span class="sxs-lookup"><span data-stu-id="baa43-109">General runtime differences</span></span>](#Runtime)  
  
-   [<span data-ttu-id="baa43-110">동적 프로그래밍 차이점</span><span class="sxs-lookup"><span data-stu-id="baa43-110">Dynamic programming differences</span></span>](#Dynamic)  
  
-   [<span data-ttu-id="baa43-111">기타 리플렉션 관련 차이점</span><span class="sxs-lookup"><span data-stu-id="baa43-111">Other reflection-related differences</span></span>](#Reflection)  
  
-   [<span data-ttu-id="baa43-112">지원되지 않는 시나리오 및 API</span><span class="sxs-lookup"><span data-stu-id="baa43-112">Unsupported scenarios and APIs</span></span>](#Unsupported)  
  
-   [<span data-ttu-id="baa43-113">Visual Studio의 차이점</span><span class="sxs-lookup"><span data-stu-id="baa43-113">Visual Studio differences</span></span>](#VS)  
  
<a name="Runtime"></a>   
## <a name="general-runtime-differences"></a><span data-ttu-id="baa43-114">일반 런타임 차이점</span><span class="sxs-lookup"><span data-stu-id="baa43-114">General runtime differences</span></span>  
  
-   <span data-ttu-id="baa43-115">예외와 같은 <xref:System.TypeLoadException>, 일반적인에서 앱 실행 될 때 JIT 컴파일러에 의해 throw 되는 언어 런타임 (CLR)는 일반적으로.NET 네이티브에서 처리 하는 경우 컴파일 타임 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-115">Exceptions, such as <xref:System.TypeLoadException>, that are thrown by the JIT compiler when an app runs on the common language runtime (CLR) generally result in compile-time errors when processed by .NET Native.</span></span>  
  
-   <span data-ttu-id="baa43-116">앱 UI 스레드에서 <xref:System.GC.WaitForPendingFinalizers%2A?displayProperty=nameWithType> 메서드를 호출해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-116">Don't call the <xref:System.GC.WaitForPendingFinalizers%2A?displayProperty=nameWithType> method from an app's UI thread.</span></span> <span data-ttu-id="baa43-117">이 인해.NET 네이티브에서 교착 상태가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-117">This can result in a deadlock on .NET Native.</span></span>  
  
-   <span data-ttu-id="baa43-118">정적 클래스 생성자 호출 순서를 따라서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-118">Don't rely on static class constructor invocation ordering.</span></span> <span data-ttu-id="baa43-119">.NET 네이티브 호출 순서는 표준 런타임의 순서와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-119">In .NET Native, the invocation order is different from the order on the standard runtime.</span></span> <span data-ttu-id="baa43-120">표준 런타임을 사용하는 경우에도 정적 클래스 생성자 실행 순서를 따라서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-120">(Even with the standard runtime, you shouldn't rely on the order of execution of static class constructors.)</span></span>  
  
-   <span data-ttu-id="baa43-121">스레드에서 호출을 하지 않고 무한 루프(예: `while(true);`)를 사용하면 앱이 중지될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-121">Infinite looping without making a call (for example, `while(true);`) on any thread may bring the app to a halt.</span></span> <span data-ttu-id="baa43-122">마찬가지로 대기 시간이 길어지거나 무한히 계속되어도 앱이 중지될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-122">Similarly, large or infinite waits may bring the app to a halt.</span></span>  
  
-   <span data-ttu-id="baa43-123">특정 제네릭 초기화 주기의.NET 네이티브에서 예외를 throw 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-123">Certain generic initialization cycles don't throw exceptions in .NET Native.</span></span> <span data-ttu-id="baa43-124">예를 들어 다음 코드는 표준 CLR에서는 <xref:System.TypeLoadException> 예외를 throw하지만</span><span class="sxs-lookup"><span data-stu-id="baa43-124">For example, the following code throws a <xref:System.TypeLoadException> exception on the standard CLR.</span></span> <span data-ttu-id="baa43-125">.NET 네이티브에서 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-125">In .NET Native, it doesn't.</span></span>  
  
     [!code-csharp[ProjectN#8](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat1.cs#8)]  
  
-   <span data-ttu-id="baa43-126">경우에 따라.NET Framework 클래스 라이브러리의 다른 구현을.NET 네이티브 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-126">In some cases, .NET Native provides different implementations of .NET Framework class libraries.</span></span> <span data-ttu-id="baa43-127">메서드에서 반환된 개체는 항상 반환된 형식의 멤버를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-127">An object returned from a method will always implement the members of the returned type.</span></span> <span data-ttu-id="baa43-128">그러나 지원 구현이 다르므로 기타 .NET Framework 플랫폼에서와 같이 해당 개체를 동일한 형식 집합으로 캐스팅하지 못할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-128">However, since its backing implementation is different, you may not be able to cast it to the same set of types as you could on other .NET Framework platforms.</span></span> <span data-ttu-id="baa43-129">예를 들어 <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Reflection.TypeInfo.DeclaredMembers%2A?displayProperty=nameWithType> 등의 메서드가 반환한 <xref:System.Reflection.TypeInfo.DeclaredProperties%2A?displayProperty=nameWithType> 인터페이스 개체는 `T[]`로 캐스팅할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-129">For example, in some cases, you may not be able to cast the <xref:System.Collections.Generic.IEnumerable%601> interface object returned by methods such as <xref:System.Reflection.TypeInfo.DeclaredMembers%2A?displayProperty=nameWithType> or <xref:System.Reflection.TypeInfo.DeclaredProperties%2A?displayProperty=nameWithType> to `T[]`.</span></span>  
  
-   <span data-ttu-id="baa43-130">WinInet 캐시는.NET에 대 한 Windows 스토어 앱에서 기본적으로 활성화 되어 있지 않으면 이지만.NET 네이티브에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-130">The WinInet cache isn't enabled by default on .NET for Windows Store apps, but it is on .NET Native.</span></span> <span data-ttu-id="baa43-131">이로 인해 성능은 향상되지만 작업 집합이 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-131">This improves performance but has working set implications.</span></span> <span data-ttu-id="baa43-132">개발자가 작업을 수행할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-132">No developer action is necessary.</span></span>  
  
<a name="Dynamic"></a>   
## <a name="dynamic-programming-differences"></a><span data-ttu-id="baa43-133">동적 프로그래밍 차이점</span><span class="sxs-lookup"><span data-stu-id="baa43-133">Dynamic programming differences</span></span>  
 <span data-ttu-id="baa43-134">.NET 네이티브 앱-로컬 성능 최대화 하기 위해 코드를 확인 하려면.NET Framework 코드에서 연결 정적으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-134">.NET Native statically links in code from the .NET Framework to make the code app-local for maximum performance.</span></span> <span data-ttu-id="baa43-135">그러나 이진 크기를 작게 유지해야 하므로 전체 .NET Framework의 코드를 가져올 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-135">However, binary sizes have to remain small, so the entire .NET Framework can't be brought in.</span></span> <span data-ttu-id="baa43-136">.NET 네이티브 컴파일러는 사용 되지 않는 코드에 대 한 참조를 제거 하는 종속성 감소 기능을 사용 하 여이 제한을 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-136">The .NET Native compiler resolves this limitation by using a dependency reducer that removes references to unused code.</span></span> <span data-ttu-id="baa43-137">그러나.NET 네이티브 수 유지 관리 않거나 정보는 컴파일 타임에 정적으로 유추할 수 없습니다. 하지만 대신는 런타임에 동적으로 검색 하는 경우 일부 형식 정보 및 코드를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-137">However, .NET Native might not maintain or generate some type information and code when that information can't be inferred statically at compile time, but instead is retrieved dynamically at runtime.</span></span>  
  
 <span data-ttu-id="baa43-138">.NET 네이티브에서는 리플렉션과 동적 프로그래밍 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-138">.NET Native does enable reflection and dynamic programming.</span></span> <span data-ttu-id="baa43-139">그러나 이로 인해 생성되는 코드 크기가 너무 커지며 특히 .NET Framework에서는 공용 API에 대한 리플렉션이 지원되지 않기 때문에 일부 형식만 리플렉션하도록 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-139">However, not all types can be marked for reflection, because this would make the generated code size too large (especially because reflecting on public APIs in the .NET Framework is supported).</span></span> <span data-ttu-id="baa43-140">.NET 네이티브 컴파일러는 적절 하 게 선택에 대 한 형식에 리플렉션을 지원 해야 하 고 메타 데이터를 유지 하 고 해당 형식에 대해서만 코드를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-140">The .NET Native compiler makes smart choices about which types should support reflection, and it keeps the metadata and generates code only for those types.</span></span>  
  
 <span data-ttu-id="baa43-141">예를 들어 데이터 바인딩을 사용하려면 앱이 속성 이름을 함수에 매핑할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-141">For example, data binding requires an app to be able to map property names to functions.</span></span> <span data-ttu-id="baa43-142">Windows 스토어 앱용 .NET에서는 공용 언어 런타임이 리플렉션을 자동으로 사용하여 관리되는 형식 및 공개적으로 사용 가능한 네이티브 형식에 대해 이 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-142">In .NET for Windows Store apps, the common language runtime automatically uses reflection to provide this capability for managed types and publicly available native types.</span></span> <span data-ttu-id="baa43-143">.NET 네이티브 컴파일러는 자동으로 데이터를 바인딩할 수 있는 형식에 대 한 메타 데이터를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-143">In .NET Native, the compiler automatically includes metadata for types to which you bind data.</span></span>  
  
 <span data-ttu-id="baa43-144">.NET 네이티브 컴파일러를 일반적으로 처리할 수도 있습니다 사용 되는 제네릭 형식의 같은 <xref:System.Collections.Generic.List%601> 및 <xref:System.Collections.Generic.Dictionary%602>는 지시문 또는 힌트 없이 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-144">The .NET Native compiler can also handle commonly used generic types such as <xref:System.Collections.Generic.List%601> and <xref:System.Collections.Generic.Dictionary%602>, which work without requiring any hints or directives.</span></span> <span data-ttu-id="baa43-145">[동적](~/docs/csharp/language-reference/keywords/dynamic.md) 키워드도 일정한 제한 내에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-145">The [dynamic](~/docs/csharp/language-reference/keywords/dynamic.md) keyword is also supported within certain limits.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="baa43-146">.NET 네이티브로 앱을 이식 하는 경우 모든 동적 코드 경로 철저 하 게 테스트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-146">You should test all dynamic code paths thoroughly when porting your app to .NET Native.</span></span>  
  
 <span data-ttu-id="baa43-147">.NET 네이티브에 대 한 기본 구성은 대부분의 개발자를 위한 충분 하지만 일부 개발자가 구성의 런타임 지시문을 사용 하 여 미세 조정 하려고 합니다. (. rd.xml) 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-147">The default configuration for .NET Native is sufficient for most developers, but some developers might want to fine- tune their configurations by using a runtime directives (.rd.xml) file.</span></span> <span data-ttu-id="baa43-148">또한 경우에 따라.NET 네이티브 컴파일러가 메타 데이터 리플렉션에 사용할 수 있어야 하며 다음과 같은 경우에 특히 힌트에 의존을 결정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-148">In addition, in some cases, the .NET Native compiler is unable to determine which metadata must be available for reflection and relies on hints, particularly in the following cases:</span></span>  
  
-   <span data-ttu-id="baa43-149"><xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType>, <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=nameWithType> 등의 일부 구문은 정적으로 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-149">Some constructs like <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> and <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=nameWithType> can't be determined statically.</span></span>  
  
-   <span data-ttu-id="baa43-150">컴파일러는 인스턴스화를 확인할 수 없으므로 런타임 지시문을 사용하여 리플렉션을 수행하려는 제네릭 형식을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-150">Because the compiler can't determine the instantiations, a generic type that you want to reflect on has to be specified by runtime directives.</span></span> <span data-ttu-id="baa43-151">이는 단순히 모든 코드를 포함해야 하기 때문이 아니라, 제네릭 형식에 대해 리플렉션을 수행하면 무한 주기가 생성될 수 있기 때문입니다(예: 제네릭 형식에 대해 제네릭 메서드를 호출하는 경우).</span><span class="sxs-lookup"><span data-stu-id="baa43-151">This isn't just because all code must be included, but because reflection on generic types can form an infinite cycle (for example, when a generic method is invoked on a generic type).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="baa43-152">런타임 지시문은 런타임 지시문(.rd.xml) 파일에서 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-152">Runtime directives are defined in a runtime directives (.rd.xml) file.</span></span> <span data-ttu-id="baa43-153">이 파일의 사용 방법에 대한 일반 정보는 [시작](../../../docs/framework/net-native/getting-started-with-net-native.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="baa43-153">For general information about using this file, see [Getting Started](../../../docs/framework/net-native/getting-started-with-net-native.md).</span></span> <span data-ttu-id="baa43-154">런타임 지시문에 대한 자세한 내용은 [Runtime Directives (rd.xml) Configuration File Reference](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="baa43-154">For information about the runtime directives, see [Runtime Directives (rd.xml) Configuration File Reference](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).</span></span>  
  
 <span data-ttu-id="baa43-155">.NET 네이티브 또한 기본 집합 이외에 형식 리플렉션을 지원 하는지 확인 하는 개발자를 지 원하는 도구를 프로 파일링 합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-155">.NET Native also includes profiling tools that help the developer determine which types outside the default set should support reflection.</span></span>  
  
<a name="Reflection"></a>   
## <a name="other-reflection-related-differences"></a><span data-ttu-id="baa43-156">기타 리플렉션 관련 차이점</span><span class="sxs-lookup"><span data-stu-id="baa43-156">Other reflection-related differences</span></span>  
 <span data-ttu-id="baa43-157">다른 개별 리플렉션 관련 동작의 차이 Windows 스토어 앱 용.NET 및.NET 네이티브의 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-157">There are a number of other individual reflection-related differences in behavior between the .NET for Windows Store apps and .NET Native.</span></span>  
  
 <span data-ttu-id="baa43-158">.NET 네이티브:</span><span class="sxs-lookup"><span data-stu-id="baa43-158">In .NET Native:</span></span>  
  
-   <span data-ttu-id="baa43-159">.NET Framework 클래스 라이브러리의 형식 및 멤버에 대한 개인 리플렉션은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-159">Private reflection over types and members in the .NET Framework class library is not supported.</span></span> <span data-ttu-id="baa43-160">그러나 고유한 개인 형식과 멤버 및 타사 라이브러리의 형식과 멤버에 대해서는 리플렉션을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-160">You can, however, reflect over your own private types and members, as well as types and members in third-party libraries.</span></span>  
  
-   <span data-ttu-id="baa43-161"><xref:System.Reflection.ParameterInfo.HasDefaultValue%2A?displayProperty=nameWithType> 속성은 반환 값을 나타내는 `false` 개체에 대해 <xref:System.Reflection.ParameterInfo>를 올바르게 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-161">The <xref:System.Reflection.ParameterInfo.HasDefaultValue%2A?displayProperty=nameWithType> property correctly returns `false` for a <xref:System.Reflection.ParameterInfo> object that represents a return value.</span></span> <span data-ttu-id="baa43-162">그러나 Windows 스토어 앱용 .NET에서는 `true`가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-162">In the .NET for Windows Store apps, it returns `true`.</span></span> <span data-ttu-id="baa43-163">IL(중간 언어)은 이러한 반환을 직접 지원하지 않으며 해석은 언어에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-163">Intermediate language (IL) doesn’t support this directly, and interpretation is left to the language.</span></span>  
  
-   <span data-ttu-id="baa43-164"><xref:System.RuntimeFieldHandle> 및 <xref:System.RuntimeMethodHandle> 구조체에서는 public 멤버를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-164">Public members on the <xref:System.RuntimeFieldHandle> and <xref:System.RuntimeMethodHandle> structures aren't supported.</span></span> <span data-ttu-id="baa43-165">이러한 형식은 LINQ, 식 트리 및 정적 배열 초기화에서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-165">These types are supported only for LINQ, expression trees, and static array initialization.</span></span>  
  
-   <span data-ttu-id="baa43-166"><xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeProperties%2A?displayProperty=nameWithType> 및 <xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeEvents%2A?displayProperty=nameWithType>의 기본 클래스는 숨겨진 멤버를 포함하므로 명시적으로 재정의하지 않아도 재정의될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-166"><xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeProperties%2A?displayProperty=nameWithType> and <xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeEvents%2A?displayProperty=nameWithType> include hidden members in base classes and thus may be overridden without explicit overrides.</span></span> <span data-ttu-id="baa43-167">이는 다른 [RuntimeReflectionExtensions.GetRuntime\*](http://msdn.microsoft.com/library/system.reflection.runtimereflectionextensions_methods.aspx) 메서드에서도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-167">This is also true of other [RuntimeReflectionExtensions.GetRuntime\*](http://msdn.microsoft.com/library/system.reflection.runtimereflectionextensions_methods.aspx) methods.</span></span>  
  
-   <span data-ttu-id="baa43-168">byref 배열과 같은 특정 조합을 만들 때 <xref:System.Type.MakeArrayType%2A?displayProperty=nameWithType> 및 <xref:System.Type.MakeByRefType%2A?displayProperty=nameWithType>에서 오류가 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-168"><xref:System.Type.MakeArrayType%2A?displayProperty=nameWithType> and <xref:System.Type.MakeByRefType%2A?displayProperty=nameWithType> don't fail when you try to create certain combinations (for example, an array of byrefs).</span></span>  
  
-   <span data-ttu-id="baa43-169">리플렉션을 사용하여 포인터 매개 변수가 있는 멤버를 호출할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-169">You can't use reflection to invoke members that have pointer parameters.</span></span>  
  
-   <span data-ttu-id="baa43-170">리플렉션을 사용하여 포인터 필드를 가져오거나 설정할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-170">You can't use reflection to get or set a pointer field.</span></span>  
  
-   <span data-ttu-id="baa43-171">인수 개수가 잘못 되었습니다. 인수 중 하나의 형식이 잘못 되었습니다.을.NET 네이티브를 throw 하는 <xref:System.ArgumentException> of를 <xref:System.Reflection.TargetParameterCountException>입니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-171">When the argument count is wrong and the type of one of the arguments is incorrect, .NET Native throws an <xref:System.ArgumentException> instead of a <xref:System.Reflection.TargetParameterCountException>.</span></span>  
  
-   <span data-ttu-id="baa43-172">예외의 이진 serialization은 일반적으로 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-172">Binary serialization of exceptions is generally not supported.</span></span> <span data-ttu-id="baa43-173">그러므로 serialize할 수 없는 개체를 <xref:System.Exception.Data%2A?displayProperty=nameWithType> 사전에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-173">As a result, non-serializable objects can be added to the <xref:System.Exception.Data%2A?displayProperty=nameWithType> dictionary.</span></span>  
  
<a name="Unsupported"></a>   
## <a name="unsupported-scenarios-and-apis"></a><span data-ttu-id="baa43-174">지원되지 않는 시나리오 및 API</span><span class="sxs-lookup"><span data-stu-id="baa43-174">Unsupported scenarios and APIs</span></span>  
 <span data-ttu-id="baa43-175">다음 섹션에서는 일반 개발, interop 및 HTTPClient, WCF(Windows Communication Foundation) 등의 기술에 대해 지원되지 않는 시나리오와 API에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-175">The following sections list unsupported scenarios and APIs for general development, interop, and technologies such as HTTPClient and Windows Communication Foundation (WCF):</span></span>  
  
-   [<span data-ttu-id="baa43-176">일반 개발</span><span class="sxs-lookup"><span data-stu-id="baa43-176">General development</span></span>](#General)  
  
-   [<span data-ttu-id="baa43-177">HttpClient</span><span class="sxs-lookup"><span data-stu-id="baa43-177">HttpClient</span></span>](#HttpClient)  
  
-   [<span data-ttu-id="baa43-178">Interop</span><span class="sxs-lookup"><span data-stu-id="baa43-178">Interop</span></span>](#Interop)  
  
-   [<span data-ttu-id="baa43-179">지원되지 않는 API</span><span class="sxs-lookup"><span data-stu-id="baa43-179">Unsupported APIs</span></span>](#APIs)  
  
<a name="General"></a>   
### <a name="general-development-differences"></a><span data-ttu-id="baa43-180">일반 개발 관련 차이점</span><span class="sxs-lookup"><span data-stu-id="baa43-180">General development differences</span></span>  
 <span data-ttu-id="baa43-181">**값 형식**</span><span class="sxs-lookup"><span data-stu-id="baa43-181">**Value types**</span></span>  
  
-   <span data-ttu-id="baa43-182">값 형식에 대해 <xref:System.ValueType.Equals%2A?displayProperty=nameWithType> 및 <xref:System.ValueType.GetHashCode%2A?displayProperty=nameWithType> 메서드를 재정의하는 경우 기본 클래스 구현을 호출하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="baa43-182">If you override the <xref:System.ValueType.Equals%2A?displayProperty=nameWithType> and <xref:System.ValueType.GetHashCode%2A?displayProperty=nameWithType> methods for a value type, don't call the base class implementations.</span></span> <span data-ttu-id="baa43-183">Windows 스토어 앱용 .NET에서 이러한 메서드는 리플렉션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-183">In .NET for Windows Store apps, these methods rely on reflection.</span></span> <span data-ttu-id="baa43-184">컴파일 타임에.NET 네이티브 않는 구현을 생성 런타임 리플렉션을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-184">At compile time, .NET Native generates an implementation that doesn't rely on runtime reflection.</span></span> <span data-ttu-id="baa43-185">이 이러한 두 메서드를 재정의 하지 않는 경우는 예상 대로 작동 하는지,.NET 네이티브 컴파일 타임에 구현을 생성 하기 때문에 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-185">This means that if you don't override these two methods, they will work as expected, because .NET Native generates the implementation at compile time.</span></span> <span data-ttu-id="baa43-186">그러나 이러한 메서드를 재정의하고 기본 클래스 구현을 호출하면 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-186">However, overriding these methods but calling the base class implementation results in an exception.</span></span>  
  
-   <span data-ttu-id="baa43-187">1MB보다 큰 값 형식은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-187">Value types larger than one megabyte aren't supported.</span></span>  
  
-   <span data-ttu-id="baa43-188">.NET 네이티브 값 형식에 기본 생성자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-188">Value types can't have a default constructor in .NET Native.</span></span> <span data-ttu-id="baa43-189">C# 및 Visual Basic에서는 값 형식에 대해 기본 생성자를 사용할 수 없지만</span><span class="sxs-lookup"><span data-stu-id="baa43-189">(C# and Visual Basic prohibit default constructors on value types.</span></span> <span data-ttu-id="baa43-190">IL에서는 기본 생성자를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-190">However, these can be created in IL.)</span></span>  
  
 <span data-ttu-id="baa43-191">**배열**</span><span class="sxs-lookup"><span data-stu-id="baa43-191">**Arrays**</span></span>  
  
-   <span data-ttu-id="baa43-192">하한이 0이 아닌 배열은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-192">Arrays with a lower bound other than zero aren't supported.</span></span> <span data-ttu-id="baa43-193">이러한 배열은 대개 <xref:System.Array.CreateInstance%28System.Type%2CSystem.Int32%5B%5D%2CSystem.Int32%5B%5D%29?displayProperty=nameWithType> 오버로드를 호출하여 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-193">Typically, these arrays are created by calling the <xref:System.Array.CreateInstance%28System.Type%2CSystem.Int32%5B%5D%2CSystem.Int32%5B%5D%29?displayProperty=nameWithType> overload.</span></span>  
  
-   <span data-ttu-id="baa43-194">동적으로 다차원 배열을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-194">Dynamic creation of multidimensional arrays isn't supported.</span></span> <span data-ttu-id="baa43-195">이러한 배열은 대개 <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> 매개 변수를 포함하는 `lengths` 메서드의 오버로드 또는 <xref:System.Type.MakeArrayType%28System.Int32%29?displayProperty=nameWithType> 메서드를 호출하여 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-195">Such arrays are typically created by calling an overload of the <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> method that includes a `lengths` parameter, or by calling the <xref:System.Type.MakeArrayType%28System.Int32%29?displayProperty=nameWithType> method.</span></span>  
  
-   <span data-ttu-id="baa43-196">차원이 4개 이상(해당 <xref:System.Array.Rank%2A?displayProperty=nameWithType> 속성 값이 4 이상)인 다차원 배열은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-196">Multidimensional arrays that have four or more dimensions aren't supported; that is, their <xref:System.Array.Rank%2A?displayProperty=nameWithType> property value is four or greater.</span></span> <span data-ttu-id="baa43-197">이러한 경우에는 [가변 배열](~/docs/csharp/programming-guide/arrays/jagged-arrays.md) (배열의 배열)을 대신 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-197">Use [jagged arrays](~/docs/csharp/programming-guide/arrays/jagged-arrays.md) (an array of arrays) instead.</span></span> <span data-ttu-id="baa43-198">예를 들어 `array[x,y,z]` 는 유효하지 않지만 `array[x][y][z]` 는 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-198">For example, `array[x,y,z]` is invalid, but `array[x][y][z]` isn't.</span></span>  
  
-   <span data-ttu-id="baa43-199">다차원 배열에는 가변성(variance)이 지원되지 않으며, 가변성(variance)을 적용하는 경우 런타임에 <xref:System.InvalidCastException> 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-199">Variance for multidimensional arrays isn't supported and causes an <xref:System.InvalidCastException> exception at run time.</span></span>  
  
 <span data-ttu-id="baa43-200">**제네릭**</span><span class="sxs-lookup"><span data-stu-id="baa43-200">**Generics**</span></span>  
  
-   <span data-ttu-id="baa43-201">무한 제네릭 형식을 확장하면 컴파일러 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-201">Infinite generic type expansion results in a compiler error.</span></span> <span data-ttu-id="baa43-202">예를 들어 다음 코드는 컴파일되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-202">For example, this code fails to compile:</span></span>  
  
     [!code-csharp[ProjectN#9](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat2.cs#9)]  
  
 <span data-ttu-id="baa43-203">**포인터**</span><span class="sxs-lookup"><span data-stu-id="baa43-203">**Pointers**</span></span>  
  
-   <span data-ttu-id="baa43-204">포인터 배열은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-204">Arrays of pointers aren't supported.</span></span>  
  
-   <span data-ttu-id="baa43-205">리플렉션을 사용하여 포인터 필드를 가져오거나 설정할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-205">You can't use reflection to get or set a pointer field.</span></span>  
  
 <span data-ttu-id="baa43-206">**serialization**</span><span class="sxs-lookup"><span data-stu-id="baa43-206">**Serialization**</span></span>  
  
 <span data-ttu-id="baa43-207"><xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.String%29> 특성은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-207">The <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.String%29> attribute isn't supported.</span></span> <span data-ttu-id="baa43-208">대신 <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.Type%29> 특성을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="baa43-208">Use the <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.Type%29> attribute instead.</span></span>  
  
 <span data-ttu-id="baa43-209">**리소스**</span><span class="sxs-lookup"><span data-stu-id="baa43-209">**Resources**</span></span>  
  
 <span data-ttu-id="baa43-210"><xref:System.Diagnostics.Tracing.EventSource> 클래스에는 지역화된 리소스를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-210">The use of localized resources with the <xref:System.Diagnostics.Tracing.EventSource> class isn't supported.</span></span> <span data-ttu-id="baa43-211"><xref:System.Diagnostics.Tracing.EventSourceAttribute.LocalizationResources%2A?displayProperty=nameWithType> 속성은 지역화된 리소스를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-211">The <xref:System.Diagnostics.Tracing.EventSourceAttribute.LocalizationResources%2A?displayProperty=nameWithType> property doesn't define localized resources.</span></span>  
  
 <span data-ttu-id="baa43-212">**대리자**</span><span class="sxs-lookup"><span data-stu-id="baa43-212">**Delegates**</span></span>  
  
 <span data-ttu-id="baa43-213">`Delegate.BeginInvoke` 및 `Delegate.EndInvoke` 는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-213">`Delegate.BeginInvoke` and `Delegate.EndInvoke` aren't supported.</span></span>  
  
 <span data-ttu-id="baa43-214">**기타 API**</span><span class="sxs-lookup"><span data-stu-id="baa43-214">**Miscellaneous APIs**</span></span>  
  
-   <span data-ttu-id="baa43-215">형식에 <xref:System.Reflection.TypeInfo.GUID%2A?displayProperty=nameWithType> 특성을 적용하지 않으면 <xref:System.PlatformNotSupportedException> 속성이 <xref:System.Runtime.InteropServices.GuidAttribute> 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-215">The <xref:System.Reflection.TypeInfo.GUID%2A?displayProperty=nameWithType> property throws a <xref:System.PlatformNotSupportedException> exception if a <xref:System.Runtime.InteropServices.GuidAttribute> attribute isn't applied to the type.</span></span> <span data-ttu-id="baa43-216">GUID는 주로 COM 지원을 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-216">The GUID is used primarily for COM support.</span></span>  
  
-   <span data-ttu-id="baa43-217"><xref:System.DateTime.Parse%2A?displayProperty=nameWithType> 메서드.NET 네이티브의 간단한 날짜를 포함 하는 문자열을 올바르게 구문 분석 합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-217">The <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> method correctly parses strings that contain short dates in .NET Native.</span></span> <span data-ttu-id="baa43-218">그러나 Microsoft 기술 자료 문서 [KB2803771](http://support.microsoft.com/kb/2803771) 및 [KB2803755](http://support.microsoft.com/kb/2803755)에서 설명하는 날짜 및 시간 구문 분석 변경 내용과의 호환성은 유지되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-218">However, it doesn't maintain compatibility with the changes in date and time parsing described in the Microsoft Knowledge Base articles [KB2803771](http://support.microsoft.com/kb/2803771) and [KB2803755](http://support.microsoft.com/kb/2803755).</span></span>  
  
-   <span data-ttu-id="baa43-219"><xref:System.Numerics.BigInteger.ToString%2A?displayProperty=nameWithType> `("E")` .NET 네이티브에서 올바르게 반올림 됩니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-219"><xref:System.Numerics.BigInteger.ToString%2A?displayProperty=nameWithType> `("E")` is correctly rounded in .NET Native.</span></span> <span data-ttu-id="baa43-220">일부 CLR 버전에서는 결과 문자열이 반올림되는 대신 잘립니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-220">In some versions of the CLR, the result string is truncated instead of rounded.</span></span>  
  
<a name="HttpClient"></a>   
### <a name="httpclient-differences"></a><span data-ttu-id="baa43-221">HttpClient의 차이점</span><span class="sxs-lookup"><span data-stu-id="baa43-221">HttpClient differences</span></span>  
 <span data-ttu-id="baa43-222">.NET 네이티브를 <xref:System.Net.Http.HttpClientHandler> 클래스는 내부적으로 WinINet을 사용 (통해 합니다 [HttpBaseProtocolFilter](http://msdn.microsoft.com/library/windows/apps/windows.web.http.filters.httpbaseprotocolfilter.aspx) 클래스) 대신를 <xref:System.Net.WebRequest> 및 <xref:System.Net.WebResponse> 표준.NET에 대 한 Windows 스토어 앱에서 사용 되는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-222">In .NET Native, the <xref:System.Net.Http.HttpClientHandler> class internally uses WinINet (through the [HttpBaseProtocolFilter](http://msdn.microsoft.com/library/windows/apps/windows.web.http.filters.httpbaseprotocolfilter.aspx) class) instead of the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes used in the standard .NET for Windows Store apps.</span></span>  <span data-ttu-id="baa43-223">WinINet은 <xref:System.Net.Http.HttpClientHandler> 클래스에서 지원하는 구성 옵션 중 일부만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-223">WinINet doesn't support all the configuration options that the <xref:System.Net.Http.HttpClientHandler> class supports.</span></span>  <span data-ttu-id="baa43-224">그 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-224">As a result:</span></span>  
  
-   <span data-ttu-id="baa43-225">기능 속성 중 일부 <xref:System.Net.Http.HttpClientHandler> 반환 `false` .NET 네이티브에서 반환 하는 반면 `true` .NET에 대 한 Windows 스토어 앱 용 표준입니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-225">Some of the capability properties on <xref:System.Net.Http.HttpClientHandler> return `false` on .NET Native, whereas they return `true` in the standard .NET for Windows Store apps.</span></span>  
  
-   <span data-ttu-id="baa43-226">구성 속성의 일부 `get` 항상 접근자에서.NET 네이티브 Windows 스토어 앱 용.NET의에서 기본 구성 가능한 값과 다른 고정된 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-226">Some of the configuration property `get` accessors always return a fixed value on .NET Native that is different than the default configurable value in .NET for Windows Store apps.</span></span>  
  
 <span data-ttu-id="baa43-227">다음 하위 섹션에서 몇 가지 추가적인 동작 차이점에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-227">Some additional behavior differences are covered in the following subsections.</span></span>  
  
 <span data-ttu-id="baa43-228">**프록시**</span><span class="sxs-lookup"><span data-stu-id="baa43-228">**Proxy**</span></span>  
  
 <span data-ttu-id="baa43-229">[HttpBaseProtocolFilter](http://msdn.microsoft.com/library/windows/apps/windows.web.http.filters.httpbaseprotocolfilter.aspx) 클래스는 요청별로 프록시의 구성 또는 재정의를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-229">The [HttpBaseProtocolFilter](http://msdn.microsoft.com/library/windows/apps/windows.web.http.filters.httpbaseprotocolfilter.aspx) class doesn’t support configuring or overriding the proxy on a per-request basis.</span></span>  <span data-ttu-id="baa43-230">즉, 시스템에서 구성한 프록시 서버 또는 프록시 서버가 값에 따라.NET 네이티브에서 모든 요청에 사용 된 <xref:System.Net.Http.HttpClientHandler.UseProxy%2A?displayProperty=nameWithType> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-230">This means that all requests on .NET Native use the system-configured proxy server or no proxy server, depending on the value of the <xref:System.Net.Http.HttpClientHandler.UseProxy%2A?displayProperty=nameWithType> property.</span></span>  <span data-ttu-id="baa43-231">Windows 스토어 앱용 .NET에서는 <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> 속성을 통해 프록시 서버가 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-231">In .NET for Windows Store apps, the proxy server is defined by the <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> property.</span></span>  <span data-ttu-id="baa43-232">설정에.NET 네이티브에 <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> 이외의 값으로 `null` throw를 <xref:System.PlatformNotSupportedException> 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-232">On .NET Native, setting the <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> to a value other than `null` throws a <xref:System.PlatformNotSupportedException> exception.</span></span>  <span data-ttu-id="baa43-233"><xref:System.Net.Http.HttpClientHandler.SupportsProxy%2A?displayProperty=nameWithType> 속성이 반환 `false` .NET 네이티브에서 반환 하는 반면 `true` Windows 스토어 용.NET Framework 앱 용 표준입니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-233">The <xref:System.Net.Http.HttpClientHandler.SupportsProxy%2A?displayProperty=nameWithType> property returns `false` on .NET Native, whereas it returns `true` in the standard .NET Framework for Windows Store apps.</span></span>  
  
 <span data-ttu-id="baa43-234">**자동 리디렉션**</span><span class="sxs-lookup"><span data-stu-id="baa43-234">**Automatic redirection**</span></span>  
  
 <span data-ttu-id="baa43-235">[HttpBaseProtocolFilter](http://msdn.microsoft.com/library/windows/apps/windows.web.http.filters.httpbaseprotocolfilter.aspx) 클래스는 구성되는 최대 자동 리디렉션 수를 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-235">The [HttpBaseProtocolFilter](http://msdn.microsoft.com/library/windows/apps/windows.web.http.filters.httpbaseprotocolfilter.aspx) class doesn't allow the maximum number of automatic redirections to be configured.</span></span>  <span data-ttu-id="baa43-236">Windows 스토어 앱용 표준 .NET에서는 <xref:System.Net.Http.HttpClientHandler.MaxAutomaticRedirections%2A?displayProperty=nameWithType> 속성의 기본값이 50이며, 이 값은 수정 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-236">The value of the <xref:System.Net.Http.HttpClientHandler.MaxAutomaticRedirections%2A?displayProperty=nameWithType> property is 50 by default in the standard .NET for Windows Store apps and can be modified.</span></span> <span data-ttu-id="baa43-237">.NET 네이티브에서이 속성의 값이 10 이며 throw를 수정 하는 동안는 <xref:System.PlatformNotSupportedException> 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-237">On .NET Native, the value of this property is 10, and trying to modify it throws a <xref:System.PlatformNotSupportedException> exception.</span></span>  <span data-ttu-id="baa43-238">합니다 <xref:System.Net.Http.HttpClientHandler.SupportsRedirectConfiguration%2A?displayProperty=nameWithType> 속성이 반환 `false` .NET 네이티브에서 반환 하는 반면 `true` Windows 스토어 앱 용.NET에서에서.</span><span class="sxs-lookup"><span data-stu-id="baa43-238">The <xref:System.Net.Http.HttpClientHandler.SupportsRedirectConfiguration%2A?displayProperty=nameWithType> property returns `false` on .NET Native, whereas it returns `true` in .NET for Windows Store apps.</span></span>  
  
 <span data-ttu-id="baa43-239">**자동 압축 풀기**</span><span class="sxs-lookup"><span data-stu-id="baa43-239">**Automatic decompression**</span></span>  
  
 <span data-ttu-id="baa43-240">Windows 스토어 앱용 .NET에서는 <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A?displayProperty=nameWithType> 속성을 <xref:System.Net.DecompressionMethods.Deflate> 또는 <xref:System.Net.DecompressionMethods.GZip> 중 하나로 설정하거나, <xref:System.Net.DecompressionMethods.Deflate> 및 <xref:System.Net.DecompressionMethods.GZip> 둘 다로 설정하거나, <xref:System.Net.DecompressionMethods.None>으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-240">.NET for Windows Store apps allows you to set the <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A?displayProperty=nameWithType> property to <xref:System.Net.DecompressionMethods.Deflate>, <xref:System.Net.DecompressionMethods.GZip>, both <xref:System.Net.DecompressionMethods.Deflate> and <xref:System.Net.DecompressionMethods.GZip>, or <xref:System.Net.DecompressionMethods.None>.</span></span>  <span data-ttu-id="baa43-241">.NET 네이티브 에서만 지원 <xref:System.Net.DecompressionMethods.Deflate> 와 함께 <xref:System.Net.DecompressionMethods.GZip>, 또는 <xref:System.Net.DecompressionMethods.None>합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-241">.NET Native only supports <xref:System.Net.DecompressionMethods.Deflate> together with <xref:System.Net.DecompressionMethods.GZip>, or <xref:System.Net.DecompressionMethods.None>.</span></span>  <span data-ttu-id="baa43-242"><xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A> 속성을 <xref:System.Net.DecompressionMethods.Deflate> 또는 <xref:System.Net.DecompressionMethods.GZip> 중 하나만으로 설정하면 <xref:System.Net.DecompressionMethods.Deflate> 및 <xref:System.Net.DecompressionMethods.GZip>둘 다로 자동 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-242">Trying to set the <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A> property to either <xref:System.Net.DecompressionMethods.Deflate> or <xref:System.Net.DecompressionMethods.GZip> alone silently sets it to both <xref:System.Net.DecompressionMethods.Deflate> and <xref:System.Net.DecompressionMethods.GZip>.</span></span>  
  
 <span data-ttu-id="baa43-243">**쿠키**</span><span class="sxs-lookup"><span data-stu-id="baa43-243">**Cookies**</span></span>  
  
 <span data-ttu-id="baa43-244">쿠키 처리는 <xref:System.Net.Http.HttpClient> 및 WinINet에서 동시에 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-244">Cookie handling is performed simultaneously by <xref:System.Net.Http.HttpClient> and WinINet.</span></span>  <span data-ttu-id="baa43-245"><xref:System.Net.CookieContainer> 의 쿠키는 WinINet 쿠키 캐시의 쿠키와 결합됩니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-245">Cookies from the <xref:System.Net.CookieContainer> are combined with cookies in the WinINet cookie cache.</span></span>  <span data-ttu-id="baa43-246"><xref:System.Net.CookieContainer> 에서 쿠키를 제거하면 <xref:System.Net.Http.HttpClient> 가 쿠키를 보낼 수 없습니다. 그러나 WinINet에서 쿠키를 이미 확인했으며 사용자가 쿠키를 삭제하지 않은 경우에는 WinINet이 쿠키를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-246">Removing a cookie from <xref:System.Net.CookieContainer> prevents <xref:System.Net.Http.HttpClient> from sending the cookie, but if the cookie was already seen by WinINet, and cookies weren't deleted by the user, WinINet sends it.</span></span>  <span data-ttu-id="baa43-247"><xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.HttpClientHandler>또는 <xref:System.Net.CookieContainer> API를 사용하여 WinINet에서 프로그래밍 방식으로 쿠키를 제거할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-247">It isn't possible to programmatically remove a cookie from WinINet by using the <xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.HttpClientHandler>, or <xref:System.Net.CookieContainer> API.</span></span>  <span data-ttu-id="baa43-248"><xref:System.Net.Http.HttpClientHandler.UseCookies%2A?displayProperty=nameWithType> 속성을 `false`로 설정하면 <xref:System.Net.Http.HttpClient>만 쿠키 보내기를 중지하며 WinINet은 요청에 쿠키를 계속 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-248">Setting the <xref:System.Net.Http.HttpClientHandler.UseCookies%2A?displayProperty=nameWithType> property to `false` causes only <xref:System.Net.Http.HttpClient> to stop sending cookies; WinINet might still include its cookies in the request.</span></span>  
  
 <span data-ttu-id="baa43-249">**자격 증명**</span><span class="sxs-lookup"><span data-stu-id="baa43-249">**Credentials**</span></span>  
  
 <span data-ttu-id="baa43-250">Windows 스토어 앱용 .NET에서는 <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A?displayProperty=nameWithType> 및 <xref:System.Net.Http.HttpClientHandler.Credentials%2A?displayProperty=nameWithType> 속성이 독립적으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-250">In .NET for Windows Store apps, the <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A?displayProperty=nameWithType> and <xref:System.Net.Http.HttpClientHandler.Credentials%2A?displayProperty=nameWithType> properties work independently.</span></span>  <span data-ttu-id="baa43-251">또한 <xref:System.Net.Http.HttpClientHandler.Credentials%2A> 속성은 <xref:System.Net.ICredentials> 인터페이스를 구현하는 모든 개체를 수락합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-251">Additionally, the <xref:System.Net.Http.HttpClientHandler.Credentials%2A> property accepts any object that implements the <xref:System.Net.ICredentials> interface.</span></span>  <span data-ttu-id="baa43-252">설정에.NET 네이티브를 <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A> 속성을 `true` 발생 합니다 <xref:System.Net.Http.HttpClientHandler.Credentials%2A> 속성을 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-252">In .NET Native, setting the <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A> property to `true` causes the <xref:System.Net.Http.HttpClientHandler.Credentials%2A> property to become `null`.</span></span>  <span data-ttu-id="baa43-253">또한 <xref:System.Net.Http.HttpClientHandler.Credentials%2A> 속성은 `null`, <xref:System.Net.CredentialCache.DefaultCredentials%2A>또는 <xref:System.Net.NetworkCredential>형식 개체로만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-253">In addition, the <xref:System.Net.Http.HttpClientHandler.Credentials%2A> property can be set only to `null`, <xref:System.Net.CredentialCache.DefaultCredentials%2A>, or an object of type <xref:System.Net.NetworkCredential>.</span></span>  <span data-ttu-id="baa43-254">다른 <xref:System.Net.ICredentials> 개체(가장 널리 사용되는 항목은 <xref:System.Net.CredentialCache>)를 <xref:System.Net.Http.HttpClientHandler.Credentials%2A> 속성에 할당하면 <xref:System.PlatformNotSupportedException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-254">Assigning any other <xref:System.Net.ICredentials> object, the most popular of which is <xref:System.Net.CredentialCache>, to the <xref:System.Net.Http.HttpClientHandler.Credentials%2A> property throws a <xref:System.PlatformNotSupportedException>.</span></span>  
  
 <span data-ttu-id="baa43-255">**기타 지원되지 않거나 구성할 수 없는 기능**</span><span class="sxs-lookup"><span data-stu-id="baa43-255">**Other unsupported or unconfigurable features**</span></span>  
  
 <span data-ttu-id="baa43-256">.NET 네이티브:</span><span class="sxs-lookup"><span data-stu-id="baa43-256">In .NET Native:</span></span>  
  
-   <span data-ttu-id="baa43-257"><xref:System.Net.Http.HttpClientHandler.ClientCertificateOptions%2A?displayProperty=nameWithType> 속성의 값은 항상 <xref:System.Net.Http.ClientCertificateOption.Automatic>입니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-257">The value of the <xref:System.Net.Http.HttpClientHandler.ClientCertificateOptions%2A?displayProperty=nameWithType> property is always <xref:System.Net.Http.ClientCertificateOption.Automatic>.</span></span>  <span data-ttu-id="baa43-258">Windows 스토어 앱용 .NET에서는 기본값이 <xref:System.Net.Http.ClientCertificateOption.Manual>입니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-258">In .NET for Windows Store apps, the default is <xref:System.Net.Http.ClientCertificateOption.Manual>.</span></span>  
  
-   <span data-ttu-id="baa43-259"><xref:System.Net.Http.HttpClientHandler.MaxRequestContentBufferSize%2A?displayProperty=nameWithType> 속성은 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-259">The <xref:System.Net.Http.HttpClientHandler.MaxRequestContentBufferSize%2A?displayProperty=nameWithType> property isn't configurable.</span></span>  
  
-   <span data-ttu-id="baa43-260"><xref:System.Net.Http.HttpClientHandler.PreAuthenticate%2A?displayProperty=nameWithType> 속성은 항상 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-260">The <xref:System.Net.Http.HttpClientHandler.PreAuthenticate%2A?displayProperty=nameWithType> property is always `true`.</span></span>  <span data-ttu-id="baa43-261">Windows 스토어 앱용 .NET에서는 기본값이 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-261">In .NET for Windows Store apps, the default is `false`.</span></span>  
  
-   <span data-ttu-id="baa43-262">응답의 `SetCookie2` 헤더는 사용되지 않는 항목으로 간주되어 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-262">The `SetCookie2` header in responses is ignored as obsolete.</span></span>  
  
<a name="Interop"></a>   
### <a name="interop-differences"></a><span data-ttu-id="baa43-263">interop 차이점</span><span class="sxs-lookup"><span data-stu-id="baa43-263">Interop differences</span></span>  
 <span data-ttu-id="baa43-264">**사용되지 않는 API**</span><span class="sxs-lookup"><span data-stu-id="baa43-264">**Deprecated APIs**</span></span>  
  
 <span data-ttu-id="baa43-265">관리되는 코드와의 상호 운용성을 위해 제공되었던 사용 빈도가 낮은 여러 API가 더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-265">A number of infrequently used APIs for interoperability with managed code have been deprecated.</span></span> <span data-ttu-id="baa43-266">.NET 네이티브를 사용 하면 이러한 Api throw 할 수는 <xref:System.NotImplementedException> 또는 <xref:System.PlatformNotSupportedException> 예외 또는 컴파일러 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-266">When used with .NET Native, these APIs may throw a <xref:System.NotImplementedException> or <xref:System.PlatformNotSupportedException> exception, or result in a compiler error.</span></span> <span data-ttu-id="baa43-267">Windows 스토어 앱용 .NET에서는 이러한 API가 사용되지 않는 것으로 표시되지만 호출해도 컴파일러 오류가 아닌 컴파일러 경고가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-267">In .NET for Windows Store apps, these APIs are marked as obsolete, although calling them generates a compiler warning rather than a compiler error.</span></span>  
  
 <span data-ttu-id="baa43-268">`VARIANT` 마샬링에 대해 사용되지 않는 API는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-268">Deprecated APIs for `VARIANT` marshaling:</span></span>  
  
||  
|-|  
|<xref:System.Runtime.InteropServices.BStrWrapper?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.CurrencyWrapper?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.DispatchWrapper?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.ErrorWrapper?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.UnknownWrapper?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.VariantWrapper?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.UnmanagedType.IDispatch?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.UnmanagedType.SafeArray?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.VarEnum?displayProperty=nameWithType>|  
  
 <span data-ttu-id="baa43-269"><xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType> 지원으로 사용 하는 경우 등의 일부 시나리오에서 예외를 throw 하지만 [IDispatch](http://msdn.microsoft.com/library/windows/apps/ms221608.aspx) 또는 byref 변형 합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-269"><xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType> is supported, but it throws an exception in some scenarios, such as when it is used with [IDispatch](http://msdn.microsoft.com/library/windows/apps/ms221608.aspx) or byref variants.</span></span>  
  
 <span data-ttu-id="baa43-270">[IDispatch](http://msdn.microsoft.com/library/windows/apps/ms221608.aspx) 지원에 대해 API가 더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-270">Deprecated APIs for [IDispatch](http://msdn.microsoft.com/library/windows/apps/ms221608.aspx) support:</span></span>  
  
|<span data-ttu-id="baa43-271">형식</span><span class="sxs-lookup"><span data-stu-id="baa43-271">Type</span></span>|<span data-ttu-id="baa43-272">멤버</span><span class="sxs-lookup"><span data-stu-id="baa43-272">Member</span></span>|  
|----------|------------|  
|<xref:System.Runtime.InteropServices.ClassInterfaceType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDispatch>|  
|<xref:System.Runtime.InteropServices.ClassInterfaceType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual>|  
|<xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=nameWithType>|<span data-ttu-id="baa43-273">특성은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-273">Attribute isn't supported</span></span>|  
  
 <span data-ttu-id="baa43-274">기본 COM 이벤트에 대해 사용되지 않는 API는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-274">Deprecated APIs for classic COM events:</span></span>  
  
||  
|-|  
|<xref:System.Runtime.InteropServices.ComEventsHelper?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute>|  
  
 <span data-ttu-id="baa43-275">사용 되지 않는 Api에는 <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> 인터페이스를.NET 네이티브에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-275">Deprecated APIs in the <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> interface, which isn't supported in .NET Native:</span></span>  
  
|<span data-ttu-id="baa43-276">형식</span><span class="sxs-lookup"><span data-stu-id="baa43-276">Type</span></span>|<span data-ttu-id="baa43-277">멤버</span><span class="sxs-lookup"><span data-stu-id="baa43-277">Member</span></span>|  
|----------|------------|  
|<xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType>|<span data-ttu-id="baa43-278">모든 멤버</span><span class="sxs-lookup"><span data-stu-id="baa43-278">All members.</span></span>|  
|<xref:System.Runtime.InteropServices.CustomQueryInterfaceMode?displayProperty=nameWithType>|<span data-ttu-id="baa43-279">모든 멤버</span><span class="sxs-lookup"><span data-stu-id="baa43-279">All members.</span></span>|  
|<xref:System.Runtime.InteropServices.CustomQueryInterfaceResult?displayProperty=nameWithType>|<span data-ttu-id="baa43-280">모든 멤버</span><span class="sxs-lookup"><span data-stu-id="baa43-280">All members.</span></span>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.GetComInterfaceForObject%28System.Object%2CSystem.Type%2CSystem.Runtime.InteropServices.CustomQueryInterfaceMode%29?displayProperty=nameWithType>|  
  
 <span data-ttu-id="baa43-281">기타 지원되지 않는 interop 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-281">Other unsupported interop features:</span></span>  
  
|<span data-ttu-id="baa43-282">형식</span><span class="sxs-lookup"><span data-stu-id="baa43-282">Type</span></span>|<span data-ttu-id="baa43-283">멤버</span><span class="sxs-lookup"><span data-stu-id="baa43-283">Member</span></span>|  
|----------|------------|  
|<xref:System.Runtime.InteropServices.ICustomAdapter?displayProperty=nameWithType>|<span data-ttu-id="baa43-284">모든 멤버</span><span class="sxs-lookup"><span data-stu-id="baa43-284">All members.</span></span>|  
|<xref:System.Runtime.InteropServices.SafeBuffer?displayProperty=nameWithType>|<span data-ttu-id="baa43-285">모든 멤버</span><span class="sxs-lookup"><span data-stu-id="baa43-285">All members.</span></span>|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.UnmanagedType.Currency>|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.UnmanagedType.VBByRefStr>|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.UnmanagedType.AnsiBStr>|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.UnmanagedType.AsAny>|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.UnmanagedType.CustomMarshaler>|  
  
 <span data-ttu-id="baa43-286">거의 사용되지 않는 마샬링 API는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-286">Rarely used marshalling APIs:</span></span>  
  
|<span data-ttu-id="baa43-287">형식</span><span class="sxs-lookup"><span data-stu-id="baa43-287">Type</span></span>|<span data-ttu-id="baa43-288">멤버</span><span class="sxs-lookup"><span data-stu-id="baa43-288">Member</span></span>|  
|----------|------------|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.ReadByte%28System.Object%2CSystem.Int32%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.ReadInt16%28System.Object%2CSystem.Int32%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.ReadInt32%28System.Object%2CSystem.Int32%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.ReadInt64%28System.Object%2CSystem.Int32%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.ReadIntPtr%28System.Object%2CSystem.Int32%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.WriteByte%28System.Object%2CSystem.Int32%2CSystem.Byte%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.WriteInt16%28System.Object%2CSystem.Int32%2CSystem.Int16%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.WriteInt32%28System.Object%2CSystem.Int32%2CSystem.Int32%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.WriteInt64%28System.Object%2CSystem.Int32%2CSystem.Int64%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.WriteIntPtr%28System.Object%2CSystem.Int32%2CSystem.IntPtr%29>|  
  
 <span data-ttu-id="baa43-289">**플랫폼 호출 및 COM interop 호환성**</span><span class="sxs-lookup"><span data-stu-id="baa43-289">**Platform invoke and COM interop compatibility**</span></span>  
  
 <span data-ttu-id="baa43-290">대부분의 플랫폼 호출 및 COM interop 시나리오는.NET 네이티브에서 계속 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-290">Most platform invoke and COM interop scenarios are still supported in .NET Native.</span></span> <span data-ttu-id="baa43-291">특히 WinRT(Windows 런타임) API와의 모든 상호 운용성 및 Windows 런타임에 필요한 모든 마샬링은 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-291">In particular, all interoperability with Windows Runtime (WinRT) APIs and all marshaling required for the Windows Runtime is supported.</span></span> <span data-ttu-id="baa43-292">여기에는 다음에 대한 마샬링 지원이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-292">This includes marshaling support for:</span></span>  
  
-   <span data-ttu-id="baa43-293">배열(<xref:System.Runtime.InteropServices.UnmanagedType.ByValArray?displayProperty=nameWithType> 포함)</span><span class="sxs-lookup"><span data-stu-id="baa43-293">Arrays (including <xref:System.Runtime.InteropServices.UnmanagedType.ByValArray?displayProperty=nameWithType>)</span></span>  
  
-   `BStr`  
  
-   <span data-ttu-id="baa43-294">대리자</span><span class="sxs-lookup"><span data-stu-id="baa43-294">Delegates</span></span>  
  
-   <span data-ttu-id="baa43-295">문자열(유니코드, ANSI 및 HSTRING)</span><span class="sxs-lookup"><span data-stu-id="baa43-295">Strings (Unicode, Ansi, and HSTRING)</span></span>  
  
-   <span data-ttu-id="baa43-296">구조체(`byref` 및 `byval`)</span><span class="sxs-lookup"><span data-stu-id="baa43-296">Structs (`byref` and `byval`)</span></span>  
  
-   <span data-ttu-id="baa43-297">Unions</span><span class="sxs-lookup"><span data-stu-id="baa43-297">Unions</span></span>  
  
-   <span data-ttu-id="baa43-298">Win32 핸들</span><span class="sxs-lookup"><span data-stu-id="baa43-298">Win32 handles</span></span>  
  
-   <span data-ttu-id="baa43-299">모든 WinRT 구문</span><span class="sxs-lookup"><span data-stu-id="baa43-299">All WinRT constructs</span></span>  
  
-   <span data-ttu-id="baa43-300">Variant 형식 마샬링에 대한 부분 지원.</span><span class="sxs-lookup"><span data-stu-id="baa43-300">Partial support for marshaling variant types.</span></span> <span data-ttu-id="baa43-301">지원되는 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-301">The following are supported:</span></span>  
  
    -   <xref:System.Boolean>  
  
    -   <xref:System.Byte>  
  
    -   <xref:System.Decimal>  
  
    -   <xref:System.Double>  
  
    -   <xref:System.Int16>  
  
    -   <xref:System.Int32>  
  
    -   <xref:System.Int64>  
  
    -   <xref:System.SByte>  
  
    -   <xref:System.Single>  
  
    -   <xref:System.UInt16>  
  
    -   <xref:System.UInt32>  
  
    -   <xref:System.UInt64>  
  
    -   `BStr`  
  
    -   [<span data-ttu-id="baa43-302">IUnknown</span><span class="sxs-lookup"><span data-stu-id="baa43-302">IUnknown</span></span>](http://msdn.microsoft.com/library/windows/desktop/ms680509.aspx)  
  
 <span data-ttu-id="baa43-303">그러나.NET 네이티브 지원 하지 않습니다 다음.</span><span class="sxs-lookup"><span data-stu-id="baa43-303">However, .NET Native doesn't support the following:</span></span>  
  
-   <span data-ttu-id="baa43-304">기본 COM 이벤트 사용</span><span class="sxs-lookup"><span data-stu-id="baa43-304">Using classic COM events</span></span>  
  
-   <span data-ttu-id="baa43-305">관리되는 형식에서 <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> 인터페이스 구현</span><span class="sxs-lookup"><span data-stu-id="baa43-305">Implementing the <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> interface on a managed type</span></span>  
  
-   <span data-ttu-id="baa43-306">구현 된 [IDispatch](http://msdn.microsoft.com/library/windows/apps/ms221608.aspx) 인터페이스를 통해 관리 되는 형식에는 <xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=nameWithType> 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-306">Implementing the [IDispatch](http://msdn.microsoft.com/library/windows/apps/ms221608.aspx) interface on a managed type through the <xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=nameWithType> attribute.</span></span> <span data-ttu-id="baa43-307">그러나 `IDispatch`를 통해 COM 개체를 호출할 수는 없으며 관리되는 개체는 `IDispatch`를 구현할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-307">However, note that you can't call COM objects through `IDispatch`, and your managed object can't implement `IDispatch`.</span></span>  
  
 <span data-ttu-id="baa43-308">리플렉션을 사용하여 플랫폼 호출 메서드를 호출할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-308">Using reflection to invoke a platform invoke method isn't supported.</span></span> <span data-ttu-id="baa43-309">대신 다른 메서드에서 메서드 호출을 래핑하고 리플렉션을 사용해 래퍼를 호출하여 이 제한을 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-309">You can work around this limitation by wrapping the method call in another method and using reflection to call the wrapper instead.</span></span>  
  
<a name="APIs"></a>   
### <a name="other-differences-from-net-apis-for-windows-store-apps"></a><span data-ttu-id="baa43-310">Windows 스토어 앱용 .NET API의 기타 차이점</span><span class="sxs-lookup"><span data-stu-id="baa43-310">Other differences from .NET APIs for Windows Store apps</span></span>  
 <span data-ttu-id="baa43-311">이 섹션에는.NET 네이티브에서 지원 되지 않는 나머지 Api를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-311">This section lists the remaining APIs that aren't supported in .NET Native.</span></span> <span data-ttu-id="baa43-312">지원되지 않는 API의 대부분은 WCF(Windows Communication Foundation) API입니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-312">The largest set of the unsupported APIs are Windows Communication Foundation (WCF) APIs.</span></span>  
  
 <span data-ttu-id="baa43-313">**DataAnnotations(System.ComponentModel.DataAnnotations)**</span><span class="sxs-lookup"><span data-stu-id="baa43-313">**DataAnnotations (System.ComponentModel.DataAnnotations)**</span></span>  
  
 <span data-ttu-id="baa43-314">형식에는 <xref:System.ComponentModel.DataAnnotations> 고 <xref:System.ComponentModel.DataAnnotations.Schema> 네임 스페이스는.NET 네이티브에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-314">The types in the <xref:System.ComponentModel.DataAnnotations> and <xref:System.ComponentModel.DataAnnotations.Schema> namespaces aren't supported in .NET Native.</span></span> <span data-ttu-id="baa43-315">여기에는 Windows 8의 Windows 스토어 앱용 .NET에서 제공되는 다음과 같은 형식이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-315">These include the following types that are present in the .NET for Windows Store apps for Windows 8:</span></span>  
  
||  
|-|  
|<xref:System.ComponentModel.DataAnnotations.AssociationAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.ConcurrencyCheckAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.CustomValidationAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.DataType?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.DataTypeAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.DisplayAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.DisplayColumnAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.DisplayFormatAttribute>|  
|<xref:System.ComponentModel.DataAnnotations.EditableAttribute>|  
|<xref:System.ComponentModel.DataAnnotations.EnumDataTypeAttribute>|  
|<xref:System.ComponentModel.DataAnnotations.FilterUIHintAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.KeyAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.RangeAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.RegularExpressionAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.RequiredAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.StringLengthAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.TimestampAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.UIHintAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.ValidationContext?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.ValidationException?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.ValidationResult?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.Validator?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.Schema.DatabaseGeneratedAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.Schema.DatabaseGeneratedOption?displayProperty=nameWithType>|  
  
 <span data-ttu-id="baa43-316">**Visual Basic**</span><span class="sxs-lookup"><span data-stu-id="baa43-316">**Visual Basic**</span></span>  
  
 <span data-ttu-id="baa43-317">Visual Basic.NET 네이티브에서 현재 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-317">Visual Basic isn't currently supported in .NET Native.</span></span> <span data-ttu-id="baa43-318">다음 형식은 합니다 <xref:Microsoft.VisualBasic> 및 <xref:Microsoft.VisualBasic.CompilerServices> 네임 스페이스를.NET 네이티브에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-318">The following types in the <xref:Microsoft.VisualBasic> and <xref:Microsoft.VisualBasic.CompilerServices> namespaces aren't available in .NET Native:</span></span>  
  
||  
|-|  
|<xref:Microsoft.VisualBasic.CallType?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.Constants?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.HideModuleNameAttribute?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.Strings?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.Conversions?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.DesignerGeneratedAttribute?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.IncompleteInitialization?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.NewLateBinding?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.ObjectFlowControl?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.ObjectFlowControl.ForLoopControl?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.Operators?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.OptionCompareAttribute?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.OptionTextAttribute?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.ProjectData?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.StandardModuleAttribute?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.StaticLocalInitFlag?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.Utils?displayProperty=nameWithType>|  
  
 <span data-ttu-id="baa43-319">**리플렉션 컨텍스트(System.Reflection.Context 네임스페이스)**</span><span class="sxs-lookup"><span data-stu-id="baa43-319">**Reflection Context (System.Reflection.Context namespace)**</span></span>  
  
 <span data-ttu-id="baa43-320"><xref:System.Reflection.Context.CustomReflectionContext?displayProperty=nameWithType> 클래스는.NET 네이티브에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-320">The <xref:System.Reflection.Context.CustomReflectionContext?displayProperty=nameWithType> class isn't supported in .NET Native.</span></span>  
  
 <span data-ttu-id="baa43-321">**RTC(System.Net.Http.Rtc)**</span><span class="sxs-lookup"><span data-stu-id="baa43-321">**RTC (System.Net.Http.Rtc)**</span></span>  
  
 <span data-ttu-id="baa43-322"><xref:System.Net.Http.RtcRequestFactory?displayProperty=nameWithType> 클래스는.NET 네이티브에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-322">The <xref:System.Net.Http.RtcRequestFactory?displayProperty=nameWithType> class isn't supported in .NET Native.</span></span>  
  
 <span data-ttu-id="baa43-323">**Windows Communication Foundation (WCF) (System.ServiceModel.\*)**</span><span class="sxs-lookup"><span data-stu-id="baa43-323">**Windows Communication Foundation (WCF) (System.ServiceModel.\*)**</span></span>  
  
 <span data-ttu-id="baa43-324">형식에는 [namespaces](http://msdn.microsoft.com/library/gg145010.aspx) .NET 네이티브에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-324">The types in the [System.ServiceModel.\* namespaces](http://msdn.microsoft.com/library/gg145010.aspx) aren't supported in .NET Native.</span></span> <span data-ttu-id="baa43-325">여기에는 다음과 같은 형식이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-325">These includes the following types:</span></span>  
  
||  
|-|  
|<xref:System.ServiceModel.ActionNotSupportedException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.BasicHttpMessageCredentialType?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.BasicHttpSecurity?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.BasicHttpSecurityMode?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.CallbackBehaviorAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ClientBase%601.BeginOperationDelegate?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ClientBase%601.ChannelBase%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ClientBase%601.EndOperationDelegate?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ClientBase%601.InvokeAsyncCompletedEventArgs?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.CommunicationException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.CommunicationObjectAbortedException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.CommunicationObjectFaultedException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.CommunicationState?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.DataContractFormatAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.DnsEndpointIdentity?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.DuplexChannelFactory%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.DuplexClientBase%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.EndpointAddress?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.EndpointAddressBuilder?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.EndpointIdentity?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.EndpointNotFoundException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.EnvelopeVersion?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ExceptionDetail?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.FaultCode?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.FaultException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.FaultReason?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.FaultReasonText?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.HttpBindingBase?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.HttpClientCredentialType?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.HttpTransportSecurity?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ICommunicationObject?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.IContextChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.IDefaultCommunicationTimeouts?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.IExtensibleObject%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.IExtension%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.IExtensionCollection%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.InvalidMessageContractException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.MessageBodyMemberAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.MessageContractAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.MessageContractMemberAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.MessageCredentialType?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.MessageHeader%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.MessageHeaderException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.MessageParameterAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.MessageSecurityOverTcp?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.MessageSecurityVersion?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.NetHttpBinding?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.NetHttpMessageEncoding?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.NetTcpBinding?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.NetTcpSecurity?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.OperationContext?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.OperationContextScope?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.OperationContractAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.OperationFormatStyle?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ProtocolException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.QuotaExceededException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.SecurityMode?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ServerTooBusyException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ServiceActivationException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ServiceKnownTypeAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.SpnEndpointIdentity?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.TcpClientCredentialType?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.TcpTransportSecurity?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.TransferMode?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.UnknownMessageReceivedEventArgs?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.UpnEndpointIdentity?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.XmlSerializerFormatAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.AddressHeader?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.AddressHeaderCollection?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.AddressingVersion?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.ChannelManagerBase?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.ChannelParameterCollection?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.CommunicationObject?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.CompressionFormat?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.FaultConverter?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.HttpRequestMessageProperty?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.HttpResponseMessageProperty?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.HttpsTransportBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IChannelFactory?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IChannelFactory%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IDuplexChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IDuplexSession?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IDuplexSessionChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IHttpCookieContainerManager?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IInputChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IInputSession?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IInputSessionChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IMessageProperty?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IOutputChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IOutputSession?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IOutputSessionChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IRequestChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IRequestSessionChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.ISession?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.ISessionChannel%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.LocalClientSecuritySettings?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.Message?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageBuffer?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageEncoder?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageEncoderFactory?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageEncodingBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageFault?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageHeader?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageHeaderInfo?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageHeaders?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageProperties?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageState?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageVersion?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.RequestContext?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.SecurityBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.SecurityHeaderLayout?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.TcpConnectionPoolSettings?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.TcpTransportBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.TransportBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.TransportSecurityBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.WebSocketTransportSettings?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.WebSocketTransportUsage?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.ClientCredentials?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.ContractDescription?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.FaultDescription?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.FaultDescriptionCollection?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessageBodyDescription?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessageDescription?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessageDescriptionCollection?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessageDirection?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessageHeaderDescription?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessageHeaderDescriptionCollection?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessagePartDescription?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessagePartDescriptionCollection?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessagePropertyDescription?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessagePropertyDescriptionCollection?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.OperationDescription?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.OperationDescriptionCollection?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.ServiceEndpoint?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Dispatcher.ClientOperation?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Dispatcher.ClientRuntime?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Dispatcher.DispatchOperation?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Dispatcher.DispatchRuntime?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Dispatcher.EndpointDispatcher?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Dispatcher.IClientMessageFormatter?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Dispatcher.IClientOperationSelector?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.BasicSecurityProfileVersion?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.HttpDigestClientCredential?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.MessageSecurityException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.SecureConversationVersion?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.SecurityAccessDeniedException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.SecurityPolicyVersion?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.SecurityVersion?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.TrustVersion?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.UserNamePasswordClientCredential?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.WindowsClientCredential?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.Tokens.SecurityTokenParameters?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.Tokens.SupportingTokenParameters?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.Tokens.UserNameSecurityTokenParameters?displayProperty=nameWithType>|  
  
### <a name="differences-in-serializers"></a><span data-ttu-id="baa43-326">serializer의 차이점</span><span class="sxs-lookup"><span data-stu-id="baa43-326">Differences in serializers</span></span>  
 <span data-ttu-id="baa43-327"><xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>및 <xref:System.Xml.Serialization.XmlSerializer> 클래스의 serialization 및 deserialization에는 다음과 같은 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-327">The following differences concern serialization and deserialization with the <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, and <xref:System.Xml.Serialization.XmlSerializer> classes:</span></span>  
  
-   <span data-ttu-id="baa43-328">.NET 네이티브 <xref:System.Runtime.Serialization.DataContractSerializer> 고 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> serialize 하거나 형식이 루트 serialization 형식이 아닌 기본 클래스 멤버가 파생된 클래스를 deserialize 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-328">In .NET Native, <xref:System.Runtime.Serialization.DataContractSerializer> and <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> fail to serialize or deserialize a derived class that has a base class member whose type isn't a root serialization type.</span></span> <span data-ttu-id="baa43-329">예를 들어 다음 코드에서 `Y` 를 serialize 또는 deserialize하려고 하면 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-329">For example, in the following code, trying to serialize or deserialize `Y` results in an error:</span></span>  
  
     [!code-csharp[ProjectN#10](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat3.cs#10)]  
  
     <span data-ttu-id="baa43-330">기본 클래스의 멤버가 serialization 중에 트래버스되지 않으므로 serializer가 `InnerType` 형식을 인식하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-330">Type `InnerType` isn't known to the serializer, because the members of the base class aren't traversed during serialization.</span></span>  
  
-   <span data-ttu-id="baa43-331"><xref:System.Runtime.Serialization.DataContractSerializer> 및 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 가 <xref:System.Collections.Generic.IEnumerable%601> 인터페이스를 구현하는 클래스나 구조체를 serialize하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-331"><xref:System.Runtime.Serialization.DataContractSerializer> and <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> fail to serialize a class or structure that implements the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="baa43-332">예를 들어 다음과 같은 형식은 serialize 또는 deserialize할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-332">For example, the following types fail to serialize or deserialize:</span></span>  
  
  
  
-   <span data-ttu-id="baa43-333"><xref:System.Xml.Serialization.XmlSerializer> 가 다음 개체 값을 serialize하지 못합니다. serialize할 정확한 개체 형식을 알 수 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-333"><xref:System.Xml.Serialization.XmlSerializer> fails to serialize the following object value, because it doesn't know the exact type of the object to be serialized:</span></span>  
  
  
  
-   <span data-ttu-id="baa43-334"><xref:System.Xml.Serialization.XmlSerializer> 는 serialize된 개체의 형식이 <xref:System.Xml.XmlQualifiedName>이면 해당 개체를 serialize 또는 deserialize할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-334"><xref:System.Xml.Serialization.XmlSerializer> fails to serialize or deserialize if the type of the serialized object is <xref:System.Xml.XmlQualifiedName>.</span></span>  
  
-   <span data-ttu-id="baa43-335">모든 serializer(<xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 및 <xref:System.Xml.Serialization.XmlSerializer>)는 <xref:System.Xml.Linq.XElement?displayProperty=nameWithType>를 포함하는 형식 또는 <xref:System.Xml.Linq.XElement> 형식에 대해 serialization 코드를 생성하지 못하며,</span><span class="sxs-lookup"><span data-stu-id="baa43-335">All serializers (<xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, and <xref:System.Xml.Serialization.XmlSerializer>) fail to generate serialization code for type <xref:System.Xml.Linq.XElement?displayProperty=nameWithType> or for a type that contains <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="baa43-336">대신 빌드 시간 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-336">They display build-time errors instead.</span></span>  
  
-   <span data-ttu-id="baa43-337">serialization 형식의 다음 생성자에 대해서는 정상적인 작동이 보장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-337">The following constructors of the serialization types aren't guaranteed to work as expected:</span></span>  
  
    -   <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29?displayProperty=nameWithType>  
  
    -   <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Runtime.Serialization.DataContractSerializerSettings%29?displayProperty=nameWithType>  
  
    -   <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.String%2CSystem.String%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29?displayProperty=nameWithType>  
  
    -   <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Xml.XmlDictionaryString%2CSystem.Xml.XmlDictionaryString%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29?displayProperty=nameWithType>  
  
    -   <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor%28System.Type%2CSystem.Runtime.Serialization.Json.DataContractJsonSerializerSettings%29?displayProperty=nameWithType>  
  
    -   <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor%28System.Type%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29?displayProperty=nameWithType>  
  
    -   <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.String%29?displayProperty=nameWithType>  
  
    -   <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Type%5B%5D%29?displayProperty=nameWithType>  
  
    -   <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlAttributeOverrides%29?displayProperty=nameWithType>  
  
    -   <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlRootAttribute%29?displayProperty=nameWithType>  
  
    -   <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlAttributeOverrides%2CSystem.Type%5B%5D%2CSystem.Xml.Serialization.XmlRootAttribute%2CSystem.String%29?displayProperty=nameWithType>  
  
-   <span data-ttu-id="baa43-338"><xref:System.Xml.Serialization.XmlSerializer> 는 메서드에 다음 특성이 포함된 형식에 대해 코드를 생성하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-338"><xref:System.Xml.Serialization.XmlSerializer> fails to generate code for a type that has methods attributed with any of the following attributes:</span></span>  
  
    -   <xref:System.Runtime.Serialization.OnSerializingAttribute>  
  
    -   <xref:System.Runtime.Serialization.OnSerializedAttribute>  
  
    -   <xref:System.Runtime.Serialization.OnDeserializingAttribute>  
  
    -   <xref:System.Runtime.Serialization.OnDeserializedAttribute>  
  
-   <span data-ttu-id="baa43-339"><xref:System.Xml.Serialization.XmlSerializer> 는 <xref:System.Xml.Serialization.IXmlSerializable> 사용자 지정 serialization 인터페이스를 따르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-339"><xref:System.Xml.Serialization.XmlSerializer> doesn't honor the <xref:System.Xml.Serialization.IXmlSerializable> custom serialization interface.</span></span> <span data-ttu-id="baa43-340">이 인터페이스를 구현하는 클래스가 있는 경우 <xref:System.Xml.Serialization.XmlSerializer> 는 해당 형식을 POCO(Plain Old CLR 개체) 형식으로 간주하여 public 속성만 serialize합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-340">If you have a class that implements this interface, <xref:System.Xml.Serialization.XmlSerializer> considers the type a plain old CLR object (POCO) type and serializes only its public properties.</span></span>  
  
-   <span data-ttu-id="baa43-341"><xref:System.Exception> 및 <xref:System.Runtime.Serialization.DataContractSerializer> 에서는 다음과 같은 일반 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>개체를 serialize할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-341">Serializing a plain <xref:System.Exception> object, such as the following, doesn't work well with <xref:System.Runtime.Serialization.DataContractSerializer> and <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>:</span></span>  
  
  
  
<a name="VS"></a>   
## <a name="visual-studio-differences"></a><span data-ttu-id="baa43-342">Visual Studio의 차이점</span><span class="sxs-lookup"><span data-stu-id="baa43-342">Visual Studio differences</span></span>  
 <span data-ttu-id="baa43-343">**예외 및 디버깅**</span><span class="sxs-lookup"><span data-stu-id="baa43-343">**Exceptions and debugging**</span></span>  
  
 <span data-ttu-id="baa43-344">디버거에서.NET 네이티브를 사용 하 여 컴파일한 앱을 실행 하는 경우 다음 예외 형식에 대 한 첫 번째 예외 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-344">When you're running apps compiled by using .NET Native in the debugger, first-chance exceptions are enabled for the following exception types:</span></span>  
  
-   <xref:System.MemberAccessException>  
  
-   <xref:System.TypeAccessException>  
  
 <span data-ttu-id="baa43-345">**앱 빌드**</span><span class="sxs-lookup"><span data-stu-id="baa43-345">**Building apps**</span></span>  
  
 <span data-ttu-id="baa43-346">Visual Studio에서 기본적으로 사용되는 x86 빌드 도구를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-346">Use the x86 build tools that are used by default by Visual Studio.</span></span> <span data-ttu-id="baa43-347">C:\Program Files (x86)\MSBuild\12.0\bin\amd64에 있는 AMD64 MSBuild 도구를 사용하는 경우 빌드 문제가 발생할 수 있으므로 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-347">We don't recommend using the AMD64 MSBuild tools, which are found in C:\Program Files (x86)\MSBuild\12.0\bin\amd64; these may create build problems.</span></span>  
  
 <span data-ttu-id="baa43-348">**프로파일러**</span><span class="sxs-lookup"><span data-stu-id="baa43-348">**Profilers**</span></span>  
  
-   <span data-ttu-id="baa43-349">Visual Studio CPU 프로파일러 및 XAML 메모리 프로파일러에 내 코드만 옵션이 올바르게 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-349">The Visual Studio CPU Profiler and XAML Memory Profiler don't display Just-My-Code correctly.</span></span>  
  
-   <span data-ttu-id="baa43-350">XAML 메모리 프로파일러에 관리되는 힙 데이터가 정확하게 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-350">The XAML Memory Profiler doesn't accurately display managed heap data.</span></span>  
  
-   <span data-ttu-id="baa43-351">CPU 프로파일러가 모듈을 올바르게 식별하지 않으며 접두사가 붙은 함수 이름을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-351">The CPU Profiler doesn't correctly identify modules, and displays prefixed function names.</span></span>  
  
 <span data-ttu-id="baa43-352">**단위 테스트 라이브러리 프로젝트**</span><span class="sxs-lookup"><span data-stu-id="baa43-352">**Unit Test Library projects**</span></span>  
  
 <span data-ttu-id="baa43-353">Windows 스토어 앱 프로젝트에 대 한 단위 테스트 라이브러리에서.NET 네이티브를 사용 하도록 설정 지원 되지 않으며 이렇게 하면 프로젝트를 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baa43-353">Enabling .NET Native on a Unit Test Library for a Windows Store apps project isn't supported and causes the project to fail to build.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baa43-354">참고 항목</span><span class="sxs-lookup"><span data-stu-id="baa43-354">See Also</span></span>  
 [<span data-ttu-id="baa43-355">시작</span><span class="sxs-lookup"><span data-stu-id="baa43-355">Getting Started</span></span>](../../../docs/framework/net-native/getting-started-with-net-native.md)  
 [<span data-ttu-id="baa43-356">런타임 지시문(rd.xml) 구성 파일 참조</span><span class="sxs-lookup"><span data-stu-id="baa43-356">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="baa43-357">.NET Windows 스토어 용 앱 개요</span><span class="sxs-lookup"><span data-stu-id="baa43-357">.NET For Windows Store apps overview</span></span>](http://msdn.microsoft.com/library/windows/apps/br230302.aspx)  
 [<span data-ttu-id="baa43-358">Windows 스토어 앱 및 Windows 런타임에 대한 .NET Framework 지원</span><span class="sxs-lookup"><span data-stu-id="baa43-358">.NET Framework Support for Windows Store Apps and Windows Runtime</span></span>](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
