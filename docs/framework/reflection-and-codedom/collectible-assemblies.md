---
title: 동적 형식 생성을 위해 수집 가능한 어셈블리
description: ''
ms.date: 08/29/2017
helpviewer_keywords:
- reflection, dynamic assembly
- assemblies, collectible
- collectible assemblies, retrieving
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 04a04e422fec14055d8ac3f50b9f2f18658a0f9f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33398263"
---
# <a name="collectible-assemblies-for-dynamic-type-generation"></a><span data-ttu-id="7da64-102">동적 형식 생성을 위해 수집 가능한 어셈블리</span><span class="sxs-lookup"><span data-stu-id="7da64-102">Collectible assemblies for dynamic type generation</span></span>

<span data-ttu-id="7da64-103">*수집 가능한 어셈블리*는 만들어진 응용 프로그램 도메인을 언로드하지 않고 언로드할 수 있는 동적 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="7da64-103">*Collectible assemblies* are dynamic assemblies that can be unloaded without unloading the application domain in which they were created.</span></span> <span data-ttu-id="7da64-104">수집 가능한 어셈블리에서 사용되는 모든 관리 및 관리되지 않는 메모리 및 포함하는 형식은 회수될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7da64-104">All managed and unmanaged memory used by a collectible assembly and the types it contains can be reclaimed.</span></span> <span data-ttu-id="7da64-105">어셈블리 이름 등의 정보는 내부 테이블에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="7da64-105">Information such as the assembly name is removed from internal tables.</span></span>

<span data-ttu-id="7da64-106">언로드를 활성화하려면 동적 어셈블리를 만들 때 <xref:System.Reflection.Emit.AssemblyBuilderAccess.RunAndCollect?displayProperty=nameWithType> 플래그를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7da64-106">To enable unloading, use the <xref:System.Reflection.Emit.AssemblyBuilderAccess.RunAndCollect?displayProperty=nameWithType> flag when you create a dynamic assembly.</span></span> <span data-ttu-id="7da64-107">어셈블리는 일시적이며(즉, 저장될 수 없음) [수집 가능한 어셈블리에 대한 제한](#restrictions-on-collectible-assemblies) 섹션에 설명된 제한 사항이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7da64-107">The assembly is transient (that is, it cannot be saved) and is subject to limitations described in the [Restrictions on Collectible Assemblies](#restrictions-on-collectible-assemblies) section.</span></span> <span data-ttu-id="7da64-108">CLR(공용 언어 런타임)은 어셈블리와 관련된 모든 개체를 릴리스할 때 자동으로 수집 가능한 어셈블리를 언로드합니다.</span><span class="sxs-lookup"><span data-stu-id="7da64-108">The common language runtime (CLR) unloads a collectible assembly automatically when you release all objects associated with the assembly.</span></span> <span data-ttu-id="7da64-109">다른 모든 측면에서 수집 가능한 어셈블리는 다른 동적 어셈블리와 동일한 방식으로 생성 및 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7da64-109">In all other respects, collectible assemblies are created and used in the same way as other dynamic assemblies.</span></span>

## <a name="lifetime-of-collectible-assemblies"></a><span data-ttu-id="7da64-110">수집 가능한 어셈블리의 수명</span><span class="sxs-lookup"><span data-stu-id="7da64-110">Lifetime of collectible assemblies</span></span>

<span data-ttu-id="7da64-111">수집 가능한 어셈블리의 수명은 포함하는 형식 및 이러한 형식에서 생성된 개체에 대한 참조의 존재 여부에 따라 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="7da64-111">The lifetime of a collectible assembly is controlled by the existence of references to the types it contains and the objects that are created from those types.</span></span> <span data-ttu-id="7da64-112">공용 언어 런타임은 다음 중 하나 이상이 있는 한 어셈블리를 언로드하지 않습니다(`T`는 어셈블리에 정의된 모든 형식).</span><span class="sxs-lookup"><span data-stu-id="7da64-112">The common language runtime does not unload an assembly as long as one or more of the following exist (`T` is any type that is defined in the assembly):</span></span> 

- <span data-ttu-id="7da64-113">`T`의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="7da64-113">An instance of `T`.</span></span>

- <span data-ttu-id="7da64-114">`T` 배열의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="7da64-114">An instance of an array of `T`.</span></span>
 
- <span data-ttu-id="7da64-115">형식 인수 중 하나로 `T`를 가진 제네릭 형식의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="7da64-115">An instance of a generic type that has `T` as one of its type arguments.</span></span> <span data-ttu-id="7da64-116">해당 컬렉션이 비어 있는 경우에도 `T`의 제네릭 컬렉션을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7da64-116">This includes generic collections of `T`, even if that collection is empty.</span></span>

- <span data-ttu-id="7da64-117">`T`를 나타내는 <xref:System.Type> 또는 <xref:System.Reflection.Emit.TypeBuilder>의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="7da64-117">An instance of <xref:System.Type> or <xref:System.Reflection.Emit.TypeBuilder> that represents `T`.</span></span> 

   > [!IMPORTANT]
   > <span data-ttu-id="7da64-118">어셈블리의 부분을 나타내는 모든 개체를 릴리스해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7da64-118">You must release all objects that represent parts of the assembly.</span></span> <span data-ttu-id="7da64-119">`T`를 정의하는 <xref:System.Reflection.Emit.ModuleBuilder>는 <xref:System.Reflection.Emit.TypeBuilder>에 대한 참조를 유지하고, <xref:System.Reflection.Emit.AssemblyBuilder> 개체는 <xref:System.Reflection.Emit.ModuleBuilder>에 대한 참조를 유지하므로 이러한 개체에 대한 참조를 릴리스해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7da64-119">The <xref:System.Reflection.Emit.ModuleBuilder> that defines `T` keeps a reference to the <xref:System.Reflection.Emit.TypeBuilder>, and the <xref:System.Reflection.Emit.AssemblyBuilder> object keeps a reference to the <xref:System.Reflection.Emit.ModuleBuilder>, so references to these objects must be released.</span></span> <span data-ttu-id="7da64-120">`T`의 생성에 사용되는 <xref:System.Reflection.Emit.LocalBuilder> 또는 <xref:System.Reflection.Emit.ILGenerator>의 존재는 언로드를 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="7da64-120">Even the existence of a <xref:System.Reflection.Emit.LocalBuilder> or an <xref:System.Reflection.Emit.ILGenerator> used in the construction of `T` prevents unloading.</span></span>

- <span data-ttu-id="7da64-121">코드를 실행하여 계속 연결할 수 있는 다른 동적으로 정의된 유형 `T1`별 `T`에 대한 정적 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="7da64-121">A static reference to `T` by another dynamically defined type `T1` that is still reachable by executing code.</span></span> <span data-ttu-id="7da64-122">예를 들어 `T1`은 `T`에서 파생될 수 있거나 `T`는 `T1`의 메서드에서 매개 변수의 형식이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7da64-122">For example, `T1` might derive from `T`, or `T` might be the type of a parameter in a method of `T1`.</span></span>
 
- <span data-ttu-id="7da64-123">`T`에 속해 있는 정적 필드에 대한 **ByRef**입니다.</span><span class="sxs-lookup"><span data-stu-id="7da64-123">A **ByRef** to a static field that belongs to `T`.</span></span>

- <span data-ttu-id="7da64-124">`T`를 참조하는 <xref:System.RuntimeTypeHandle>, <xref:System.RuntimeFieldHandle> 또는 <xref:System.RuntimeMethodHandle>, 또는 `T`의 구성 요소에 대한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7da64-124">A <xref:System.RuntimeTypeHandle>, <xref:System.RuntimeFieldHandle>, or <xref:System.RuntimeMethodHandle> that refers to `T` or to a component of `T`.</span></span>

- <span data-ttu-id="7da64-125">`T`를 나타내는 <xref:System.Type> 개체에 대한 액세스에 간접적 또는 직접적으로 사용될 수 있는 모든 리플렉션 개체의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="7da64-125">An instance of any reflection object that could be used indirectly or directly to access the <xref:System.Type> object that represents `T`.</span></span> <span data-ttu-id="7da64-126">예를 들어 `T`에 대한 <xref:System.Type> 개체는 요소 형식이 `T`인 배열 형식에서 또는 형식 인수로 `T`를 가진 제네릭 형식에서 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7da64-126">For example, the <xref:System.Type> object for `T` can be obtained from an array type whose element type is `T`, or from a generic type that has `T` as a type argument.</span></span> 

- <span data-ttu-id="7da64-127">`M`이 `T`의 메서드이거나 어셈블리에 정의된 모듈 수준 메서드인 모든 스레드의 호출 스택에 있는 메서드 `M`입니다.</span><span class="sxs-lookup"><span data-stu-id="7da64-127">A method `M` on the call stack of any thread, where `M` is a method of `T` or a module-level method that is defined in the assembly.</span></span>

- <span data-ttu-id="7da64-128">어셈블리의 모듈에 정의된 정적 메서드에 대한 대리자입니다.</span><span class="sxs-lookup"><span data-stu-id="7da64-128">A delegate to a static method that is defined in a module of the assembly.</span></span>

<span data-ttu-id="7da64-129">이 목록의 한 항목만 어셈블리에서 하나의 형식 또는 한 개의 메서드에 대해 있는 경우 런타임은 어셈블리를 언로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7da64-129">If only one item from this list exists for only one type or one method in the assembly, the runtime cannot unload the assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="7da64-130">런타임은 종료자가 목록의 모든 항목에 대해 실행될 때까지 어셈블리를 실제로 언로드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7da64-130">The runtime does not actually unload the assembly until finalizers have run for all items in the list.</span></span>

<span data-ttu-id="7da64-131">수명 추적을 위해 수집 가능한 어셈블리의 생성에서 만들어지고 사용된 `List<int>`(C#에서) 또는 `List(Of Integer)`(Visual Basic에서)와 같은 생성된 제네릭 형식은 제네릭 형식 정의를 포함하는 어셈블리 또는 해당 형식 인수 중 하나의 정의를 포함하는 어셈블리에서 정의된 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="7da64-131">For purposes of tracking lifetime, a constructed generic type such as `List<int>` (in C#) or `List(Of Integer)` (in Visual Basic) that is created and used in the generation of a collectible assembly is considered to have been defined either in the assembly that contains the generic type definition or in an assembly that contains the definition of one of its type arguments.</span></span> <span data-ttu-id="7da64-132">사용되는 정확한 어셈블리는 구현 세부 정보이며 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7da64-132">The exact assembly that is used is an implementation detail and subject to change.</span></span>
 
## <a name="restrictions-on-collectible-assemblies"></a><span data-ttu-id="7da64-133">수집 가능한 어셈블리에 대한 제한 사항</span><span class="sxs-lookup"><span data-stu-id="7da64-133">Restrictions on collectible assemblies</span></span>

<span data-ttu-id="7da64-134">수집 가능한 어셈블리에는 다음과 같은 제약 조건이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7da64-134">The following restrictions apply to collectible assemblies:</span></span> 

- <span data-ttu-id="7da64-135">**정적 참조** </span><span class="sxs-lookup"><span data-stu-id="7da64-135">**Static references** </span></span>  
  <span data-ttu-id="7da64-136">일반 동적 어셈블리의 형식은 수집 가능한 어셈블리에서 정의된 형식에 대한 정적 참조를 가질 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7da64-136">Types in an ordinary dynamic assembly cannot have static references to types that are defined in a collectible assembly.</span></span> <span data-ttu-id="7da64-137">예를 들어 수집 가능한 어셈블리의 형식에서 상속되는 일반 형식을 정의하는 경우는 <xref:System.NotSupportedException> 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="7da64-137">For example, if you define an ordinary type that inherits from a type in a collectible assembly, a <xref:System.NotSupportedException> exception is thrown.</span></span> <span data-ttu-id="7da64-138">수집 가능한 어셈블리의 형식은 다른 수집 가능한 어셈블리의 형식에 대한 정적 참조를 가질 수 있지만 이는 참조된 어셈블리의 수명을 참조하는 어셈블리의 수명으로 연장합니다.</span><span class="sxs-lookup"><span data-stu-id="7da64-138">A type in a collectible assembly can have static references to a type in another collectible assembly, but this extends the lifetime of the referenced assembly to the lifetime of the referencing assembly.</span></span>

- <span data-ttu-id="7da64-139">**COM interop** </span><span class="sxs-lookup"><span data-stu-id="7da64-139">**COM interop** </span></span>  
   <span data-ttu-id="7da64-140">COM 인터페이스는 수집 가능한 어셈블리 내에서 정의될 수 없으며 수집 가능한 어셈블리 내의 형식 인스턴스는 COM 개체로 변환될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7da64-140">No COM interfaces can be defined within a collectible assembly, and no instances of types within a collectible assembly can be converted into COM objects.</span></span> <span data-ttu-id="7da64-141">수집 가능한 어셈블리의 형식은 CCW(COM 호출 가능 래퍼) 또는 RCW(런타임 호출 가능 래퍼)로 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7da64-141">A type in a collectible assembly cannot serve as a COM callable wrapper (CCW) or runtime callable wrapper (RCW).</span></span> <span data-ttu-id="7da64-142">그러나 수집 가능한 어셈블리의 형식은 COM 인터페이스를 구현하는 개체를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7da64-142">However, types in collectible assemblies can use objects that implement COM interfaces.</span></span>

- <span data-ttu-id="7da64-143">**플랫폼 호출** </span><span class="sxs-lookup"><span data-stu-id="7da64-143">**Platform invoke** </span></span>  
   <span data-ttu-id="7da64-144"><xref:System.Runtime.InteropServices.DllImportAttribute> 특성이 있는 메서드는 수집 가능한 어셈블리에서 선언될 때 컴파일하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7da64-144">Methods that have the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute will not compile when they are declared in a collectible assembly.</span></span> <span data-ttu-id="7da64-145"><xref:System.Reflection.Emit.OpCodes.Calli?displayProperty=nameWithType> 명령은 수집 가능한 어셈블리에서 형식의 구현에 사용할 수 없으며 이러한 형식은 비관리 코드로 마샬링될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7da64-145">The <xref:System.Reflection.Emit.OpCodes.Calli?displayProperty=nameWithType> instruction cannot be used in the implementation of a type in a collectible assembly, and such types cannot be marshaled to unmanaged code.</span></span> <span data-ttu-id="7da64-146">그러나 수집 불가능한 어셈블리에서 선언된 진입점을 사용하여 네이티브 코드로 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7da64-146">However, you can call into native code by using an entry point that is declared in a non-collectible assembly.</span></span>
 
- <span data-ttu-id="7da64-147">**마샬링** </span><span class="sxs-lookup"><span data-stu-id="7da64-147">**Marshaling** </span></span>  
   <span data-ttu-id="7da64-148">수집 가능한 어셈블리에서 정의된 개체(특히 대리자)는 마샬링될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7da64-148">Objects (in particular, delegates) that are defined in collectible assemblies cannot be marshaled.</span></span> <span data-ttu-id="7da64-149">이는 모든 임시 내보낸 형식에 대한 제한입니다.</span><span class="sxs-lookup"><span data-stu-id="7da64-149">This is a restriction on all transient emitted types.</span></span>

- <span data-ttu-id="7da64-150">**어셈블리 로딩** </span><span class="sxs-lookup"><span data-stu-id="7da64-150">**Assembly loading** </span></span>  
   <span data-ttu-id="7da64-151">리플렉션 내보내기는 수집 가능한 어셈블리 로드에 대해 지원되는 유일한 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="7da64-151">Reflection emit is the only mechanism that is supported for loading collectible assemblies.</span></span> <span data-ttu-id="7da64-152">다른 형태의 어셈블리 로드를 사용하여 로드되는 어셈블리를 언로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7da64-152">Assemblies that are loaded by using any other form of assembly loading cannot be unloaded.</span></span>
 
- <span data-ttu-id="7da64-153">**컨텍스트 바인딩 개체**  </span><span class="sxs-lookup"><span data-stu-id="7da64-153">**Context-bound objects**  </span></span>  
   <span data-ttu-id="7da64-154">컨텍스트 정적 변수는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7da64-154">Context-static variables are not supported.</span></span> <span data-ttu-id="7da64-155">수집 가능한 어셈블리의 형식은 <xref:System.ContextBoundObject>를 확장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7da64-155">Types in a collectible assembly cannot extend <xref:System.ContextBoundObject>.</span></span> <span data-ttu-id="7da64-156">그러나 수집 가능한 어셈블리의 코드는 다른 곳에서 정의된 컨텍스트 바인딩 개체를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7da64-156">However, code in collectible assemblies can use context-bound objects that are defined elsewhere.</span></span>

- <span data-ttu-id="7da64-157">**스레드 정적 데이터**     </span><span class="sxs-lookup"><span data-stu-id="7da64-157">**Thread-static data**     </span></span>  
   <span data-ttu-id="7da64-158">스레드 정적 변수는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7da64-158">Thread-static variables are not supported.</span></span>

## <a name="see-also"></a><span data-ttu-id="7da64-159">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7da64-159">See also</span></span>

[<span data-ttu-id="7da64-160">동적 메서드 및 어셈블리 내보내기</span><span class="sxs-lookup"><span data-stu-id="7da64-160">Emitting Dynamic Methods and Assemblies</span></span>](emitting-dynamic-methods-and-assemblies.md)
