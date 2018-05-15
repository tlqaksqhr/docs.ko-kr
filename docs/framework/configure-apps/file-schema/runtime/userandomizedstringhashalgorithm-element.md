---
title: '&lt;UseRandomizedStringHashAlgorithm&gt; 요소'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UseRandomizedStringHashAlgorithm element
- <UseRandomizedStringHashAlgorithm> element
ms.assetid: c08125d6-56cc-4b23-b482-813ff85dc630
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a515c3011905c4f5c18ed9d3e8edf489428c04d8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltuserandomizedstringhashalgorithmgt-element"></a><span data-ttu-id="c29c2-102">&lt;UseRandomizedStringHashAlgorithm&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="c29c2-102">&lt;UseRandomizedStringHashAlgorithm&gt; Element</span></span>
<span data-ttu-id="c29c2-103">공용 언어 런타임에서 문자열에 대 한 해시 코드를 계산할지 여부를 결정 한 응용 프로그램 도메인 단위로.</span><span class="sxs-lookup"><span data-stu-id="c29c2-103">Determines whether the common language runtime calculates hash codes for strings on a per application domain basis.</span></span>  
  
 <span data-ttu-id="c29c2-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="c29c2-104">\<configuration></span></span>  
<span data-ttu-id="c29c2-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="c29c2-105">\<runtime></span></span>  
<span data-ttu-id="c29c2-106">\<UseRandomizedStringHashAlgorithm ></span><span class="sxs-lookup"><span data-stu-id="c29c2-106">\<UseRandomizedStringHashAlgorithm></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c29c2-107">구문</span><span class="sxs-lookup"><span data-stu-id="c29c2-107">Syntax</span></span>  
  
```xml  
<UseRandomizedStringHashAlgorithm   
   enabled=0|1 />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c29c2-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c29c2-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c29c2-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c29c2-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c29c2-110">특성</span><span class="sxs-lookup"><span data-stu-id="c29c2-110">Attributes</span></span>  
  
|<span data-ttu-id="c29c2-111">특성</span><span class="sxs-lookup"><span data-stu-id="c29c2-111">Attribute</span></span>|<span data-ttu-id="c29c2-112">설명</span><span class="sxs-lookup"><span data-stu-id="c29c2-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="c29c2-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="c29c2-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="c29c2-114">문자열에 대 한 해시 코드에서 계산 되 고 있는지 여부를 지정 된 응용 프로그램 도메인 단위로.</span><span class="sxs-lookup"><span data-stu-id="c29c2-114">Specifies whether hash codes for strings are calculated on a per application domain basis.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="c29c2-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="c29c2-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="c29c2-116">값</span><span class="sxs-lookup"><span data-stu-id="c29c2-116">Value</span></span>|<span data-ttu-id="c29c2-117">설명</span><span class="sxs-lookup"><span data-stu-id="c29c2-117">Description</span></span>|  
|-----------|-----------------|  
|`0`|<span data-ttu-id="c29c2-118">공용 언어 런타임에서 문자열에 대 한 해시 코드를 계산 하지 않습니다는 응용 프로그램 도메인 단위로; 문자열 해시 코드를 계산 하는 단일 알고리즘 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c29c2-118">The common language runtime does not compute hash codes for strings on a per application domain basis; a single algorithm is used to calculate string hash codes.</span></span> <span data-ttu-id="c29c2-119">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="c29c2-119">This is the default.</span></span>|  
|`1`|<span data-ttu-id="c29c2-120">문자열에 대 한 해시 코드를 계산 하는 공용 언어 런타임에서 응용 프로그램 도메인 단위로.</span><span class="sxs-lookup"><span data-stu-id="c29c2-120">The common language runtime computes hash codes for strings on a per application domain basis.</span></span> <span data-ttu-id="c29c2-121">서로 다른 프로세스와 다른 응용 프로그램 도메인에 동일한 문자열 다른 해시 코드를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="c29c2-121">Identical strings in different application domains and in different processes will have different hash codes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c29c2-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c29c2-122">Child Elements</span></span>  
 <span data-ttu-id="c29c2-123">없음</span><span class="sxs-lookup"><span data-stu-id="c29c2-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c29c2-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c29c2-124">Parent Elements</span></span>  
  
|<span data-ttu-id="c29c2-125">요소</span><span class="sxs-lookup"><span data-stu-id="c29c2-125">Element</span></span>|<span data-ttu-id="c29c2-126">설명</span><span class="sxs-lookup"><span data-stu-id="c29c2-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c29c2-127">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="c29c2-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="c29c2-128">런타임 초기화 옵션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c29c2-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c29c2-129">설명</span><span class="sxs-lookup"><span data-stu-id="c29c2-129">Remarks</span></span>  
 <span data-ttu-id="c29c2-130">기본적으로는 <xref:System.StringComparer> 클래스 및 <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> 메서드에서 응용 프로그램 도메인 간에 일관 된 해시 코드를 생성 하는 단일 해시 알고리즘을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c29c2-130">By default, the <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method use a single hashing algorithm that produces a consistent hash code across application domains.</span></span> <span data-ttu-id="c29c2-131">이 설정에 해당 하는 `enabled` 특성에는 `<UseRandomizedStringHashAlgorithm>` 요소를 `0`합니다.</span><span class="sxs-lookup"><span data-stu-id="c29c2-131">This is equivalent to setting the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `0`.</span></span> <span data-ttu-id="c29c2-132">이에서 사용 되는 해시 알고리즘의 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="c29c2-132">This is the hashing algorithm used in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].</span></span>  
  
 <span data-ttu-id="c29c2-133"><xref:System.StringComparer> 클래스 및 <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> 메서드에 해시 코드를 계산 하는 다른 해싱 알고리즘을 사용할 수도 있습니다는 응용 프로그램 도메인 단위로.</span><span class="sxs-lookup"><span data-stu-id="c29c2-133">The <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method can also use a different hashing algorithm that computes hash codes on a per application domain basis.</span></span> <span data-ttu-id="c29c2-134">결과적으로, 해당 하는 문자열에 대 한 해시 코드는 응용 프로그램 도메인 간에 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="c29c2-134">As a result, hash codes for equivalent strings will differ across application domains.</span></span> <span data-ttu-id="c29c2-135">이 기능은 옵트인 기능이; 것을 활용 하려면 설정 해야 합니다는 `enabled` 특성에는 `<UseRandomizedStringHashAlgorithm>` 요소를 `1`합니다.</span><span class="sxs-lookup"><span data-stu-id="c29c2-135">This is an opt-in feature; to take advantage of it, you must set the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `1`.</span></span>  
  
 <span data-ttu-id="c29c2-136">문자열 조회는 해시 테이블에서 일반적으로 o (1) 연산입니다.</span><span class="sxs-lookup"><span data-stu-id="c29c2-136">The string lookup in a hash table is typically an O(1) operation.</span></span> <span data-ttu-id="c29c2-137">그러나 많은 수의 충돌이 발생 하는 경우 조회 될 수 있습니다는 O (n<sup>2</sup>) 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="c29c2-137">However, when a large number of collisions occur, the lookup can become an O(n<sup>2</sup>) operation.</span></span> <span data-ttu-id="c29c2-138">사용할 수는 `<UseRandomizedStringHashAlgorithm>` 다시 해시 코드 계산 되는 키 데이터 입력에 기반 하는 경우에 특히 잠재적 충돌 수를 제한 하는 응용 프로그램 도메인, 임의의 해시 알고리즘을 생성 하는 구성 요소 사용자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c29c2-138">You can use the `<UseRandomizedStringHashAlgorithm>` configuration element to generate a random hashing algorithm per application domain, which in turn limits the number of potential collisions, particularly when the keys from which the hash codes are calculated are based on data input by users.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c29c2-139">예제</span><span class="sxs-lookup"><span data-stu-id="c29c2-139">Example</span></span>  
 <span data-ttu-id="c29c2-140">다음 예제에서는 정의 `DisplayString` 개인 문자열 상수를 포함 하는 클래스 `s`, 해당 값은 "는 문자열입니다."</span><span class="sxs-lookup"><span data-stu-id="c29c2-140">The following example defines a `DisplayString` class that includes a private string constant, `s`, whose value is "This is a string."</span></span> <span data-ttu-id="c29c2-141">또한 포함는 `ShowStringHashCode` 문자열 값 및 메서드가 실행 되는 응용 프로그램 도메인의 이름과 함께 해시 코드를 표시 하는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="c29c2-141">It also includes a `ShowStringHashCode` method that displays the string value and its hash code along with the name of the application domain in which the method is executing.</span></span>  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 <span data-ttu-id="c29c2-142">예제 구성 파일을 제공 하지 않고 실행 하면 다음과 유사한 출력이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c29c2-142">When you run the example without supplying a configuration file, it displays output similar to the following.</span></span> <span data-ttu-id="c29c2-143">참고 두 응용 프로그램 도메인에서 문자열에 대 한 해시 코드는 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="c29c2-143">Note that the hash codes for the string are identical in the two application domains.</span></span>  
  
```  
String 'This is a string.' in domain 'PerDomain.exe': 941BCEAC  
String 'This is a string.' in domain 'NewDomain': 941BCEAC  
```  
  
 <span data-ttu-id="c29c2-144">그러나 디렉터리의 예에 다음 구성 파일을 추가 하 고 다음 예제를 실행 하는 경우 동일한 문자열에 대 한 해시 코드 응용 프로그램 도메인 별로 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="c29c2-144">However, if you add the following configuration file to the example's directory and then run the example, the hash codes for the same string will differ by application domain.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <UseRandomizedStringHashAlgorithm enabled="1" />  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="c29c2-145">구성 파일에 있는 경우의 예제는 다음과 같은 출력을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c29c2-145">When the configuration file is present, the example displays the following output:</span></span>  
  
```  
String 'This is a string.' in domain 'PerDomain.exe': 5435776D  
String 'This is a string.' in domain 'NewDomain': 75CC8236  
```  
  
## <a name="see-also"></a><span data-ttu-id="c29c2-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c29c2-146">See Also</span></span>  
 <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>  
 <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>  
 <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>
