---
title: '&lt;메서드&gt; 요소(.NET 네이티브)'
ms.date: 03/30/2017
ms.assetid: 348b49e5-589d-4eb2-a597-d6ff60ab52d1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e32b9a294f81208fe85a9e1de011daef0d1d5294
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33393340"
---
# <a name="ltmethodgt-element-net-native"></a><span data-ttu-id="0244c-102">&lt;메서드&gt; 요소(.NET 네이티브)</span><span class="sxs-lookup"><span data-stu-id="0244c-102">&lt;Method&gt; Element (.NET Native)</span></span>
<span data-ttu-id="0244c-103">생성자 또는 메서드에 런타임 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0244c-103">Applies runtime reflection policy to a constructor or method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0244c-104">구문</span><span class="sxs-lookup"><span data-stu-id="0244c-104">Syntax</span></span>  
  
```xml  
<Method Name="method_name"  
        Signature="method_signature"  
        Browse="policy_type"  
        Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0244c-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0244c-105">Attributes and Elements</span></span>  
 <span data-ttu-id="0244c-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0244c-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0244c-107">특성</span><span class="sxs-lookup"><span data-stu-id="0244c-107">Attributes</span></span>  
  
|<span data-ttu-id="0244c-108">특성</span><span class="sxs-lookup"><span data-stu-id="0244c-108">Attribute</span></span>|<span data-ttu-id="0244c-109">특성 형식</span><span class="sxs-lookup"><span data-stu-id="0244c-109">Attribute type</span></span>|<span data-ttu-id="0244c-110">설명</span><span class="sxs-lookup"><span data-stu-id="0244c-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="0244c-111">일반</span><span class="sxs-lookup"><span data-stu-id="0244c-111">General</span></span>|<span data-ttu-id="0244c-112">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="0244c-112">Required attribute.</span></span> <span data-ttu-id="0244c-113">메서드 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0244c-113">Specifies the method name.</span></span>|  
|`Signature`|<span data-ttu-id="0244c-114">일반</span><span class="sxs-lookup"><span data-stu-id="0244c-114">General</span></span>|<span data-ttu-id="0244c-115">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="0244c-115">Optional attribute.</span></span> <span data-ttu-id="0244c-116">메서드 시그니처를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0244c-116">Specifies the method signature.</span></span> <span data-ttu-id="0244c-117">매개 변수가 여러 개이면 쉼표로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="0244c-117">If multiple parameters are present, they are separated by commas.</span></span> <span data-ttu-id="0244c-118">예를 들어 다음 `<Method>` 요소는 <xref:System.DateTimeOffset.ToString%28System.String%2CSystem.IFormatProvider%29> 메서드에 대한 정책을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0244c-118">For example, the following `<Method>` element defines policy for the <xref:System.DateTimeOffset.ToString%28System.String%2CSystem.IFormatProvider%29> method.</span></span><br /><br /> `<Type Name="System.DateTime">    <Method Name="ToString" Signature="System.String,System.IFormatProvider"            Dynamic="Required" /> </Type>`<br /><br /> <span data-ttu-id="0244c-119">특성이 없으면 런타임 지시문은 메서드의 모든 오버로드에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0244c-119">If the attribute is absent, the runtime directive applies to all overloads of the method.</span></span>|  
|`Browse`|<span data-ttu-id="0244c-120">반사</span><span class="sxs-lookup"><span data-stu-id="0244c-120">Reflection</span></span>|<span data-ttu-id="0244c-121">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="0244c-121">Optional attribute.</span></span> <span data-ttu-id="0244c-122">메서드에 대한 정보 쿼리 또는 메서드 열거는 제어하지만 런타임에 동적 호출을 사용하도록 설정하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0244c-122">Controls querying for information about or enumerating a method but does not enable any dynamic invocation at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="0244c-123">반사</span><span class="sxs-lookup"><span data-stu-id="0244c-123">Reflection</span></span>|<span data-ttu-id="0244c-124">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="0244c-124">Optional attribute.</span></span> <span data-ttu-id="0244c-125">동적 프로그래밍을 수행할 수 있도록 생성자 또는 메서드에 대한 런타임 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="0244c-125">Controls runtime access to a constructor or method to enable dynamic programming.</span></span> <span data-ttu-id="0244c-126">이 정책을 사용하면 런타임에 멤버를 동적으로 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0244c-126">This policy ensures that a member can be invoked dynamically at run time.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="0244c-127">Name 특성</span><span class="sxs-lookup"><span data-stu-id="0244c-127">Name attribute</span></span>  
  
|<span data-ttu-id="0244c-128">값</span><span class="sxs-lookup"><span data-stu-id="0244c-128">Value</span></span>|<span data-ttu-id="0244c-129">설명</span><span class="sxs-lookup"><span data-stu-id="0244c-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0244c-130">*method_name*</span><span class="sxs-lookup"><span data-stu-id="0244c-130">*method_name*</span></span>|<span data-ttu-id="0244c-131">메서드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0244c-131">The method name.</span></span> <span data-ttu-id="0244c-132">메서드의 형식은 부모 [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) 또는 [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) 요소로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="0244c-132">The type of the method is defined by the parent [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) or [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="signature-attribute"></a><span data-ttu-id="0244c-133">시그니처 특성</span><span class="sxs-lookup"><span data-stu-id="0244c-133">Signature attribute</span></span>  
  
|<span data-ttu-id="0244c-134">값</span><span class="sxs-lookup"><span data-stu-id="0244c-134">Value</span></span>|<span data-ttu-id="0244c-135">설명</span><span class="sxs-lookup"><span data-stu-id="0244c-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0244c-136">*method_signature*</span><span class="sxs-lookup"><span data-stu-id="0244c-136">*method_signature*</span></span>|<span data-ttu-id="0244c-137">메서드 시그니처를 구성하는 매개 변수 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0244c-137">The parameter types that form the method signature.</span></span> <span data-ttu-id="0244c-138">매개 변수가 여러 개이면 `"System.String,System.Int32,System.Int32)"`와 같이 쉼표로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="0244c-138">Multiple parameters are separated by commas, for example, `"System.String,System.Int32,System.Int32)"`.</span></span> <span data-ttu-id="0244c-139">매개 변수 형식 이름은 정규화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0244c-139">Parameter type names should be fully qualified.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="0244c-140">기타 모든 특성</span><span class="sxs-lookup"><span data-stu-id="0244c-140">All other attributes</span></span>  
  
|<span data-ttu-id="0244c-141">값</span><span class="sxs-lookup"><span data-stu-id="0244c-141">Value</span></span>|<span data-ttu-id="0244c-142">설명</span><span class="sxs-lookup"><span data-stu-id="0244c-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0244c-143">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="0244c-143">*policy_setting*</span></span>|<span data-ttu-id="0244c-144">이 정책 형식에 적용할 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="0244c-144">The setting to apply to this policy type.</span></span> <span data-ttu-id="0244c-145">가능한 값은 `Auto`, `Excluded`, `Included` 및 `Required`입니다.</span><span class="sxs-lookup"><span data-stu-id="0244c-145">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="0244c-146">자세한 내용은 [런타임 지시문 정책 설정](../../../docs/framework/net-native/runtime-directive-policy-settings.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0244c-146">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0244c-147">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0244c-147">Child Elements</span></span>  
  
|<span data-ttu-id="0244c-148">요소</span><span class="sxs-lookup"><span data-stu-id="0244c-148">Element</span></span>|<span data-ttu-id="0244c-149">설명</span><span class="sxs-lookup"><span data-stu-id="0244c-149">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0244c-150">\<Parameter></span><span class="sxs-lookup"><span data-stu-id="0244c-150">\<Parameter></span></span>](../../../docs/framework/net-native/parameter-element-net-native.md)|<span data-ttu-id="0244c-151">메서드에 전달된 인수의 형식에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0244c-151">Applies policy to the type of the argument passed to a method.</span></span>|  
|[<span data-ttu-id="0244c-152">\<GenericParameter></span><span class="sxs-lookup"><span data-stu-id="0244c-152">\<GenericParameter></span></span>](../../../docs/framework/net-native/genericparameter-element-net-native.md)|<span data-ttu-id="0244c-153">제네릭 형식 또는 메서드의 매개 변수 형식에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0244c-153">Applies policy to the parameter type of a generic type or method.</span></span>|  
|[<span data-ttu-id="0244c-154">\<ImpliesType></span><span class="sxs-lookup"><span data-stu-id="0244c-154">\<ImpliesType></span></span>](../../../docs/framework/net-native/impliestype-element-net-native.md)|<span data-ttu-id="0244c-155">포함 `<Method>` 요소가 나타내는 메서드에 정책이 적용된 경우 형식에 해당 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0244c-155">Applies policy to a type, if that policy has been applied to the method represented by the containing `<Method>` element.</span></span>|  
|[<span data-ttu-id="0244c-156">\<TypeParameter></span><span class="sxs-lookup"><span data-stu-id="0244c-156">\<TypeParameter></span></span>](../../../docs/framework/net-native/typeparameter-element-net-native.md)|<span data-ttu-id="0244c-157">메서드로 전달된 <xref:System.Type> 인수가 나타내는 형식에 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0244c-157">Applies policy to the type represented by a <xref:System.Type> argument passed to a method.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0244c-158">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0244c-158">Parent Elements</span></span>  
  
|<span data-ttu-id="0244c-159">요소</span><span class="sxs-lookup"><span data-stu-id="0244c-159">Element</span></span>|<span data-ttu-id="0244c-160">설명</span><span class="sxs-lookup"><span data-stu-id="0244c-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0244c-161">\<Type></span><span class="sxs-lookup"><span data-stu-id="0244c-161">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="0244c-162">형식 및 모든 해당 멤버에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0244c-162">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="0244c-163">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="0244c-163">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="0244c-164">생성된 제네릭 형식 및 모든 해당 멤버에 리플렉션 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0244c-164">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0244c-165">설명</span><span class="sxs-lookup"><span data-stu-id="0244c-165">Remarks</span></span>  
 <span data-ttu-id="0244c-166">제네릭 메서드의 `<Method>` 요소는 자체 정책이 없는 모든 인스턴스화에 해당 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="0244c-166">A `<Method>` element of a generic method applies its policy to all instantiations that do not have their own policy.</span></span>  
  
 <span data-ttu-id="0244c-167">`Signature` 특성을 사용하여 특정 메서드 오버로드에 대한 정책을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0244c-167">You can use the `Signature` attribute to specify policy for a particular method overload.</span></span> <span data-ttu-id="0244c-168">`Signature` 특성이 없는 경우 런타임 지시문은 메서드의 모든 오버로드에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0244c-168">Otherwise, if the `Signature` attribute is absent, the runtime directive applies to all overloads of the method.</span></span>  
  
 <span data-ttu-id="0244c-169">`<Method>` 요소를 사용하여 생성자에 대해 런타임 리플렉션 정책을 정의할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0244c-169">You cannot define the runtime reflection policy for a constructor by using the `<Method>` element.</span></span> <span data-ttu-id="0244c-170">대신 [\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md), [\<Namespace>](../../../docs/framework/net-native/namespace-element-net-native.md), [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) 또는 [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) 요소의 `Activate` 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0244c-170">Instead, use the `Activate` attribute of the  [\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md), [\<Namespace>](../../../docs/framework/net-native/namespace-element-net-native.md), [\<Type>](../../../docs/framework/net-native/type-element-net-native.md), or [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0244c-171">예제</span><span class="sxs-lookup"><span data-stu-id="0244c-171">Example</span></span>  
 <span data-ttu-id="0244c-172">다음 예제의 `Stringify` 메서드는 리플렉션을 사용하여 개체를 문자열 표현으로 변환하는 범용 서식 지정 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="0244c-172">The `Stringify` method in the following example is a general-purpose formatting method that uses reflection to convert an object to its string representation.</span></span> <span data-ttu-id="0244c-173">이 메서드는 개체의 기본 `ToString` 메서드를 호출할 수 있을 뿐 아니라 개체의 `ToString` 메서드에 서식 문자열이나 <xref:System.IFormatProvider> 구현 중 하나 또는 둘 다를 전달하여 서식이 지정된 결과 문자열을 생성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0244c-173">In addition to calling the object's default `ToString` method, the method can produce a formatted result string by passing an object's `ToString` method a format string, an <xref:System.IFormatProvider> implementation, or both.</span></span> <span data-ttu-id="0244c-174">또한 숫자를 이진, 16진수 또는 8진수 표현으로 변환하는 <xref:System.Convert.ToString%2A?displayProperty=nameWithType> 오버로드 중 하나를 호출할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0244c-174">It can also call one of the <xref:System.Convert.ToString%2A?displayProperty=nameWithType> overloads that converts a number to its binary, hexadecimal, or octal representation.</span></span>  
  
 [!code-csharp[ProjectN_Reflection#7](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/method1.cs#7)]  
  
 <span data-ttu-id="0244c-175">다음과 같은 코드를 통해 `Stringify` 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0244c-175">The `Stringify` method can be called by code like the following:</span></span>  
  
 [!code-csharp[ProjectN_Reflection#7](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/method1.cs#7)]  
  
 <span data-ttu-id="0244c-176">그러나 이 예제를 .NET 네이티브에서 컴파일하면 런타임에 <xref:System.NullReferenceException> 및 [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) 예외를 비롯한 여러 예외가 throw될 수 있습니다. 이러한 예외가 throw되는 이유는, `Stringify` 메서드는 기본적으로 .NET Framework 클래스 라이브러리의 기본 형식에 대한 동적 서식 지정을 지원하는 데 사용되는데</span><span class="sxs-lookup"><span data-stu-id="0244c-176">However, when compiled with .NET Native, the example can throw an number of exceptions at runtime, including <xref:System.NullReferenceException> and [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) exceptions, This occurs because the `Stringify` method is intended primarily to support dynamically formatting the primitive types in the .NET Framework Class Library.</span></span> <span data-ttu-id="0244c-177">기본 지시문 파일이 해당 메타데이터를 제공하지 않기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="0244c-177">However, their metadata is not made available by the default directives file.</span></span> <span data-ttu-id="0244c-178">그러나 메타데이터가 제공되더라도 위의 예제에서는 [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) 예외가 throw됩니다. 적절한 `ToString` 구현이 네이티브 코드에 포함되지 않았기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="0244c-178">Even when their metadata is made available, however, the example throws [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) exceptions because the appropriate `ToString` implementations have not been include in the native code.</span></span>  
  
 <span data-ttu-id="0244c-179">[\<Type>](../../../docs/framework/net-native/type-element-net-native.md) 요소를 사용하여 해당 메타데이터가 있어야 하는 형식을 정의하고, `<Method>` 요소를 추가하여 동적으로 호출 가능한 메서드 오버로드 구현도 있도록 지정하면 이러한 예외를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0244c-179">These exceptions can all be eliminated by using the [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) element to define the types whose metadata must be present, and by adding `<Method>` elements to ensure that the implementation of method overloads that can be called dynamically is also present.</span></span> <span data-ttu-id="0244c-180">다음은 이러한 예외를 방지하고 예제가 오류 없이 실행되도록 하는 default.rd.xml 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="0244c-180">The following is the default.rd.xml file that eliminates these exceptions and allows the example to execute without error.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Application>  
     <Assembly Name="*Application*" Dynamic="Required All" />  
  
     <Type Name = "System.Convert" Browse="Required Public" Dynamic="Required Public" >  
        <Method Name="ToString"    Dynamic ="Required" />  
     </Type>  
     <Type Name="System.Double" Browse="Required Public">  
        <Method Name="ToString" Dynamic="Required" />  
     </Type>  
     <Type Name ="System.Int32" Browse="Required Public" >  
        <Method Name="ToString" Dynamic="Required" />  
     </Type>  
     <Type Name ="System.Int64" Browse="Required Public" >  
        <Method Name="ToString" Dynamic="Required" />  
     </Type>  
     <Namespace Name="System" >  
        <Type Name="Byte" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="DateTime" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="Decimal" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="Guid" Browse ="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="Int16" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="SByte" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="Single" Browse="Required Public" >  
          <Method Name="ToString" Dynamic="Required" />           
        </Type>  
        <Type Name="TimeSpan" Browse="Required Public" >  
          <Method Name="ToString" Dynamic="Required" />           
        </Type>  
        <Type Name="UInt16" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="UInt32" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="UInt64" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
     </Namespace>  
  </Application>  
</Directives>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0244c-181">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0244c-181">See Also</span></span>  
 [<span data-ttu-id="0244c-182">런타임 지시문(rd.xml) 구성 파일 참조</span><span class="sxs-lookup"><span data-stu-id="0244c-182">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="0244c-183">런타임 지시문 요소</span><span class="sxs-lookup"><span data-stu-id="0244c-183">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)  
 [<span data-ttu-id="0244c-184">런타임 지시문 정책 설정</span><span class="sxs-lookup"><span data-stu-id="0244c-184">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)  
 [<span data-ttu-id="0244c-185">\<MethodInstantiation> 요소</span><span class="sxs-lookup"><span data-stu-id="0244c-185">\<MethodInstantiation> Element</span></span>](../../../docs/framework/net-native/methodinstantiation-element-net-native.md)
