---
title: '방법: 클레임 비교'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- claims [WCF], comparing
- claims [WCF]
ms.assetid: 0c4ec84d-53df-408f-8953-9bc437f56c28
ms.openlocfilehash: 1ef957efcb4cc9330c1c273a1c953afc5b7dd240
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33489085"
---
# <a name="how-to-compare-claims"></a><span data-ttu-id="0e864-102">방법: 클레임 비교</span><span class="sxs-lookup"><span data-stu-id="0e864-102">How to: Compare Claims</span></span>
<span data-ttu-id="0e864-103">Windows Communication Foundation (WCF)에 Id 모델 인프라는 권한 부여 확인을 수행 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e864-103">The Identity Model infrastructure in Windows Communication Foundation (WCF) is used to perform authorization checking.</span></span> <span data-ttu-id="0e864-104">따라서 이 인프라의 일반적인 작업은 권한 부여 컨텍스트의 클레임과 요청한 작업을 수행하거나 요청한 리소스에 액세스하는 데 필요한 클레임을 비교하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0e864-104">As such, a common task is to compare claims in the authorization context to the claims required to perform the requested action or access the requested resource.</span></span> <span data-ttu-id="0e864-105">이 항목에서는 기본 제공 클레임 형식 및 사용자 지정 클레임 형식을 비롯한 클레임의 비교 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0e864-105">This topic describes how to compare claims, including built-in and custom claim types.</span></span> <span data-ttu-id="0e864-106">Id 모델 인프라에 대 한 자세한 내용은 참조 [관리 클레임 및 권한 부여 Id 모델](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0e864-106">For more information about the Identity Model infrastructure, see [Managing Claims and Authorization with the Identity Model](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md).</span></span>  
  
 <span data-ttu-id="0e864-107">클레임 비교 작업에는 클레임의 세 부분(형식, 권한 및 리소스)을 다른 클레임의 해당 부분과 같은지 비교하는 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e864-107">Claim comparison involves comparing the three parts of a claim (type, right, and resource) against the same parts in another claim to see if they are equal.</span></span> <span data-ttu-id="0e864-108">다음 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0e864-108">See the following example.</span></span>  
  
 [!code-csharp[c_CustomClaimComparison#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#9)]
 [!code-vb[c_CustomClaimComparison#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#9)]  
  
 <span data-ttu-id="0e864-109">두 클레임에는 모두 <xref:System.IdentityModel.Claims.ClaimTypes.Name%2A> 클레임 형식, <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> 권한 및 "someone" 문자열 리소스가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e864-109">Both claims have a claim type of <xref:System.IdentityModel.Claims.ClaimTypes.Name%2A>, a right of <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>, and a resource of the string "someone".</span></span> <span data-ttu-id="0e864-110">클레임의 세 부분이 모두 같기 때문에 클레임 자체가 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="0e864-110">As all three parts of the claim are equal, the claims themselves are equal.</span></span>  
  
 <span data-ttu-id="0e864-111">기본 제공 클레임 형식은 <xref:System.IdentityModel.Claims.Claim.Equals%2A> 메서드를 통해 비교됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e864-111">The built-in claim types are compared using the <xref:System.IdentityModel.Claims.Claim.Equals%2A> method.</span></span> <span data-ttu-id="0e864-112">클레임 관련 비교 코드는 필요한 경우에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e864-112">Claim-specific comparison code is used where necessary.</span></span> <span data-ttu-id="0e864-113">다음은 두 개의 UPN(User Principal Name) 클레임이 주어진 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="0e864-113">For example, given the following two user principal name (UPN) claims:</span></span>  
  
 [!code-csharp[c_CustomClaimComparison#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#4)]
 [!code-vb[c_CustomClaimComparison#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#4)]  
  
 <span data-ttu-id="0e864-114">비교 코드는 <xref:System.IdentityModel.Claims.Claim.Equals%2A> 메서드 반환 `true`되었다고 가정 하 고 `example\someone` 동일한 도메인 사용자로 식별 "someone@example.com"입니다.</span><span class="sxs-lookup"><span data-stu-id="0e864-114">the comparison code in the <xref:System.IdentityModel.Claims.Claim.Equals%2A> method returns `true`, assuming `example\someone` identifies the same domain user as "someone@example.com".</span></span>  
  
 <span data-ttu-id="0e864-115">사용자 지정 클레임 형식도 <xref:System.IdentityModel.Claims.Claim.Equals%2A> 메서드를 통해 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e864-115">Custom claim types can also be compared using the <xref:System.IdentityModel.Claims.Claim.Equals%2A> method.</span></span> <span data-ttu-id="0e864-116">하지만 클레임의 <xref:System.IdentityModel.Claims.Claim.Resource%2A> 속성에 의해 반환된 형식이 기본 형식이 아닌 경우에는 <xref:System.IdentityModel.Claims.Claim.Equals%2A> 속성에 의해 반환된 값이 `true` 메서드별로 같을 경우에만 `Resource`에서 <xref:System.IdentityModel.Claims.Claim.Equals%2A>를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0e864-116">However, in cases where the type returned by the <xref:System.IdentityModel.Claims.Claim.Resource%2A> property of the claim is something other than a primitive type, the <xref:System.IdentityModel.Claims.Claim.Equals%2A> returns `true` only if the values returned by the `Resource` properties are equal according to the <xref:System.IdentityModel.Claims.Claim.Equals%2A> method.</span></span> <span data-ttu-id="0e864-117">이러한 사항이 적합하지 않은 경우 필요한 사용자 지정 처리 작업을 수행하려면, `Resource` 속성에 의해 반환된 사용자 지정 형식을 통해 <xref:System.IdentityModel.Claims.Claim.Equals%2A> 및 <xref:System.Object.GetHashCode%2A> 메서드를 재정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e864-117">In cases where this is not appropriate, the custom type returned by the `Resource` property should override the <xref:System.IdentityModel.Claims.Claim.Equals%2A> and <xref:System.Object.GetHashCode%2A> methods to perform whatever custom processing is necessary.</span></span>  
  
### <a name="comparing-built-in-claims"></a><span data-ttu-id="0e864-118">기본 제공 클레임 비교</span><span class="sxs-lookup"><span data-stu-id="0e864-118">Comparing built-in claims</span></span>  
  
1.  <span data-ttu-id="0e864-119"><xref:System.IdentityModel.Claims.Claim> 클래스의 두 인스턴스를 고려하여, 다음 코드에서와 같이 <xref:System.IdentityModel.Claims.Claim.Equals%2A>를 사용하여 비교 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0e864-119">Given two instances of the <xref:System.IdentityModel.Claims.Claim> class, use the <xref:System.IdentityModel.Claims.Claim.Equals%2A> to make the comparison, as shown in the following code.</span></span>  
  
     [!code-csharp[c_CustomClaimComparison#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#5)]
     [!code-vb[c_CustomClaimComparison#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#5)]  
  
### <a name="comparing-custom-claims-with-primitive-resource-types"></a><span data-ttu-id="0e864-120">기본 리소스 형식을 사용하는 사용자 지정 클레임 비교</span><span class="sxs-lookup"><span data-stu-id="0e864-120">Comparing custom claims with primitive resource types</span></span>  
  
1.  <span data-ttu-id="0e864-121">기본 리소스 형식을 사용하는 사용자 지정 클레임의 경우에는 다음 코드에서와 같이 기본 제공 클레임에 대한 비교를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e864-121">For custom claims with primitive resource types, comparison can be performed as for built-in claims, as shown in the following code.</span></span>  
  
     [!code-csharp[c_CustomClaimComparison#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#6)]
     [!code-vb[c_CustomClaimComparison#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#6)]  
  
2.  <span data-ttu-id="0e864-122">구조체 또는 클래스 기반의 리소스 형식을 사용하는 사용자 지정 클레임의 경우에는 리소스 형식에서 <xref:System.IdentityModel.Claims.Claim.Equals%2A> 메서드를 재정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e864-122">For custom claims with structure or class based resource types, the resource type should override the <xref:System.IdentityModel.Claims.Claim.Equals%2A> method.</span></span>  
  
3.  <span data-ttu-id="0e864-123">우선 `obj` 매개 변수가 `null`인지 확인하고 null이면 `false`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0e864-123">First check whether the `obj` parameter is `null`, and if so, return `false`.</span></span>  
  
     [!code-csharp[c_CustomClaimComparison#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#7)]
     [!code-vb[c_CustomClaimComparison#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#7)]  
  
4.  <span data-ttu-id="0e864-124">그런 다음 <xref:System.Object.ReferenceEquals%2A>를 호출하고 `this` 및 `obj`를 매개 변수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="0e864-124">Next call <xref:System.Object.ReferenceEquals%2A> and pass `this` and `obj` as parameters.</span></span> <span data-ttu-id="0e864-125">이때 `true`를 반환하면 `true`가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e864-125">If it returns `true`, then return `true`.</span></span>  
  
     [!code-csharp[c_CustomClaimComparison#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#8)]
     [!code-vb[c_CustomClaimComparison#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#8)]  
  
5.  <span data-ttu-id="0e864-126">`obj`를 클래스 형식의 로컬 변수에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="0e864-126">Next attempt to assign `obj` to a local variable of the class type.</span></span> <span data-ttu-id="0e864-127">이 작업에 실패할 경우 참조는 `null`이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e864-127">If this fails, the reference is `null`.</span></span> <span data-ttu-id="0e864-128">이러한 경우에는 `false`가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e864-128">In such cases, return `false`.</span></span>  
  
6.  <span data-ttu-id="0e864-129">현재 클레임을 제공된 클레임과 올바르게 비교하는 데 필요한 사용자 지정 비교 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0e864-129">Perform the custom comparison necessary to correctly compare the current claim to the provided claim.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e864-130">예제</span><span class="sxs-lookup"><span data-stu-id="0e864-130">Example</span></span>  
 <span data-ttu-id="0e864-131">다음 예제에서는 클레임 리소스 형식이 기본 형식이 아닌 경우의 사용자 지정 클레임 비교에 대해 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0e864-131">The following example shows a comparison of custom claims where the claim resource is a non-primitive type.</span></span>  
  
 [!code-csharp[c_CustomClaimComparison#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#0)]
 [!code-vb[c_CustomClaimComparison#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#0)]  
  
## <a name="see-also"></a><span data-ttu-id="0e864-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0e864-132">See Also</span></span>  
 [<span data-ttu-id="0e864-133">ID 모델을 사용하여 클레임 및 권한 부여 관리</span><span class="sxs-lookup"><span data-stu-id="0e864-133">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 [<span data-ttu-id="0e864-134">방법: 사용자 지정 클레임 만들기</span><span class="sxs-lookup"><span data-stu-id="0e864-134">How to: Create a Custom Claim</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-claim.md)
