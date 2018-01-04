---
title: "방법: 사용자 지정 클레임 만들기"
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
ms.assetid: d619976b-eda3-475e-ac23-c7988a2dceb0
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 92420b993a1959b03090181944a34a32ab500733
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-custom-claim"></a><span data-ttu-id="9ea11-102">방법: 사용자 지정 클레임 만들기</span><span class="sxs-lookup"><span data-stu-id="9ea11-102">How to: Create a Custom Claim</span></span>
<span data-ttu-id="9ea11-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]의 ID 모델 인프라에서는 기본 제공 클레임 형식 및 권한 집합에 해당 형식과 권한으로 <xref:System.IdentityModel.Claims.Claim> 인스턴스를 만드는 도우미 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea11-103">The Identity Model infrastructure in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] provides a set of built-in claim types and rights with the helper functions for creating <xref:System.IdentityModel.Claims.Claim> instances with those types and rights.</span></span> <span data-ttu-id="9ea11-104">이러한 기본 제공 클레임은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 기본적으로 지원하는 클라이언트 자격 증명 형식에 있는 정보를 모델링합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea11-104">These built-in claims are designed to model information found in client credential types that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] supports by default.</span></span> <span data-ttu-id="9ea11-105">일반적으로 기본 제공 클레임으로 충분하지만 일부 응용 프로그램에는 사용자 지정 클레임이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ea11-105">In many cases, the built-in claims are sufficient; however some applications may require custom claims.</span></span> <span data-ttu-id="9ea11-106">클레임은 클레임 형식, 클레임이 적용되는 리소스 및 해당 리소스에 대해 어설션되는 권한으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ea11-106">A claim consists of the claim type, the resource for which the claim applies to and the right that is asserted over that resource.</span></span> <span data-ttu-id="9ea11-107">이 항목에서는 사용자 지정 클레임을 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea11-107">This topic describes how to create a custom claim.</span></span>  
  
### <a name="to-create-a-custom-claim-that-is-based-on-a-primitive-data-type"></a><span data-ttu-id="9ea11-108">기본 데이터 형식을 기반으로 사용자 지정 클레임을 만들려면</span><span class="sxs-lookup"><span data-stu-id="9ea11-108">To create a custom claim that is based on a primitive data type</span></span>  
  
1.  <span data-ttu-id="9ea11-109">클레임 형식, 리소스 값 및 권한을 <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29> 생성자에 전달하여 사용자 지정 클레임을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9ea11-109">Create a custom claim by passing the claim type, resource value and right to the <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29> constructor.</span></span>  
  
    1.  <span data-ttu-id="9ea11-110">클레임 형식의 고유 값을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea11-110">Decide on a unique value for the claim type.</span></span>  
  
         <span data-ttu-id="9ea11-111">클레임 형식은 고유한 문자열 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="9ea11-111">The claim type is a unique string identifier.</span></span> <span data-ttu-id="9ea11-112">클레임 형식에 사용되는 문자열 식별자를 고유하게 설정하는 작업은 사용자 지정 클레임 디자이너가 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea11-112">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the claim type is unique.</span></span> <span data-ttu-id="9ea11-113">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 정의되는 클레임 형식 목록은 <xref:System.IdentityModel.Claims.ClaimTypes> 클래스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ea11-113">For a list of claim types that are defined by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], see the <xref:System.IdentityModel.Claims.ClaimTypes> class.</span></span>  
  
    2.  <span data-ttu-id="9ea11-114">기본 데이터 형식과 리소스 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea11-114">Choose the primitive data type and value for the resource.</span></span>  
  
         <span data-ttu-id="9ea11-115">리소스는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="9ea11-115">A resource is an object.</span></span> <span data-ttu-id="9ea11-116">리소스의 CLR 형식은 기본(예: <xref:System.String> 또는 <xref:System.Int32>)이나 serialize할 수 있는 모든 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ea11-116">The CLR type of the resource can be a primitive, such as <xref:System.String> or <xref:System.Int32>, or any serializable type.</span></span> <span data-ttu-id="9ea11-117">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]가 다양한 지점에서 클레임을 serialize하므로 리소스의 CLR 형식을 serialize할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea11-117">The CLR type of the resource must be serializable, because claims are serialized at various points by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="9ea11-118">기본 형식은 serialize할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ea11-118">Primitive types are serializable.</span></span>  
  
    3.  <span data-ttu-id="9ea11-119">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 정의된 권한이나 사용자 지정 권한의 고유 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea11-119">Choose a right that is defined by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] or a unique value for a custom right.</span></span>  
  
         <span data-ttu-id="9ea11-120">권한은 고유한 문자열 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="9ea11-120">A right is a unique string identifier.</span></span> <span data-ttu-id="9ea11-121">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 정의된 권한은 <xref:System.IdentityModel.Claims.Rights> 클래스에서 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ea11-121">The rights that are defined by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] are defined in the <xref:System.IdentityModel.Claims.Rights> class.</span></span>  
  
         <span data-ttu-id="9ea11-122">권한에 사용되는 문자열 식별자를 고유하게 설정하는 작업은 사용자 지정 클레임 디자이너가 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea11-122">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the right is unique.</span></span>  
  
         <span data-ttu-id="9ea11-123">다음 코드 예제에서는 `http://example.org/claims/simplecustomclaim` 권한을 사용하여 `Driver's License`라는 리소스에 대해 클레임 형식이 <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>인 사용자 지정 클레임을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9ea11-123">The following code example creates a custom claim with a claim type of `http://example.org/claims/simplecustomclaim`, for a resource named `Driver's License`, and with the <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> right.</span></span>  
  
     [!code-csharp[c_CustomClaim#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#4)]
     [!code-vb[c_CustomClaim#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#4)]  
  
### <a name="to-create-a-custom-claim-that-is-based-on-a-non-primitive-data-type"></a><span data-ttu-id="9ea11-124">기본이 아닌 데이터 형식을 기반으로 사용자 지정 클레임을 만들려면</span><span class="sxs-lookup"><span data-stu-id="9ea11-124">To create a custom claim that is based on a non-primitive data type</span></span>  
  
1.  <span data-ttu-id="9ea11-125">클레임 형식, 리소스 값 및 권한을 <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29> 생성자에 전달하여 사용자 지정 클레임을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9ea11-125">Create a custom claim by passing the claim type, resource value and right to the <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29> constructor.</span></span>  
  
    1.  <span data-ttu-id="9ea11-126">클레임 형식의 고유 값을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea11-126">Decide on a unique value for the claim type.</span></span>  
  
         <span data-ttu-id="9ea11-127">클레임 형식은 고유한 문자열 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="9ea11-127">The claim type is a unique string identifier.</span></span> <span data-ttu-id="9ea11-128">클레임 형식에 사용되는 문자열 식별자를 고유하게 설정하는 작업은 사용자 지정 클레임 디자이너가 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea11-128">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the claim type is unique.</span></span> <span data-ttu-id="9ea11-129">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 정의되는 클레임 형식 목록은 <xref:System.IdentityModel.Claims.ClaimTypes> 클래스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ea11-129">For a list of claim types that are defined by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], see the <xref:System.IdentityModel.Claims.ClaimTypes> class.</span></span>  
  
    2.  <span data-ttu-id="9ea11-130">serialize할 수 있는 기본이 아닌 리소스 형식을 선택하거나 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea11-130">Choose or define a serializable non-primitive type for the resource.</span></span>  
  
         <span data-ttu-id="9ea11-131">리소스는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="9ea11-131">A resource is an object.</span></span> <span data-ttu-id="9ea11-132">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]가 다양한 지점에서 클레임을 serialize하므로 리소스의 CLR 형식을 serialize할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea11-132">The CLR type of the resource must be serializable, because claims are serialized at various points by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="9ea11-133">기본 형식은 이미 serialize할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ea11-133">Primitive types are already serializable.</span></span>  
  
         <span data-ttu-id="9ea11-134">새 형식을 정의하는 경우 <xref:System.Runtime.Serialization.DataContractAttribute>를 클래스에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea11-134">When a new type is defined, apply the <xref:System.Runtime.Serialization.DataContractAttribute> to the class.</span></span> <span data-ttu-id="9ea11-135">또한 클레임의 일부로 serialize할 수 있어야 하는 새 형식의 모든 멤버에 <xref:System.Runtime.Serialization.DataMemberAttribute> 특성을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea11-135">Also apply the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to the all members of the new type that need to be serialized as part of the claim.</span></span>  
  
         <span data-ttu-id="9ea11-136">다음 코드 예제에서는 `MyResourceType`이라는 사용자 지정 리소스 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea11-136">The following code example defines a custom resource type named `MyResourceType`.</span></span>  
  
         [!code-csharp[c_CustomClaim#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#2)] 
         [!code-vb[c_CustomClaim#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#2)]        
  
    3.  <span data-ttu-id="9ea11-137">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 정의된 권한이나 사용자 지정 권한의 고유 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea11-137">Choose a right that is defined by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] or a unique value for a custom right.</span></span>  
  
         <span data-ttu-id="9ea11-138">권한은 고유한 문자열 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="9ea11-138">A right is a unique string identifier.</span></span> <span data-ttu-id="9ea11-139">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 정의된 권한은 <xref:System.IdentityModel.Claims.Rights> 클래스에서 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ea11-139">The rights that are defined by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] are defined in the <xref:System.IdentityModel.Claims.Rights> class.</span></span>  
  
         <span data-ttu-id="9ea11-140">권한에 사용되는 문자열 식별자를 고유하게 설정하는 작업은 사용자 지정 클레임 디자이너가 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea11-140">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the right is unique.</span></span>  
  
         <span data-ttu-id="9ea11-141">다음 코드 예제에서는 `http://example.org/claims/complexcustomclaim` 권한을 사용하여 클레임 형식이 `MyResourceType`이고 사용자 지정 리소스 형식이 <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>인 사용자 지정 클레임을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9ea11-141">The following code example creates a custom claim with a claim type of `http://example.org/claims/complexcustomclaim`, a custom resource type of `MyResourceType`, and with the <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> right.</span></span>  
  
         [!code-csharp[c_CustomClaim#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#5)] 
         [!code-vb[c_CustomClaim#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#5)]     
  
## <a name="example"></a><span data-ttu-id="9ea11-142">예</span><span class="sxs-lookup"><span data-stu-id="9ea11-142">Example</span></span>  
 <span data-ttu-id="9ea11-143">다음 코드 예제에서는 기본 리소스 형식의 사용자 지정 클레임과 기본이 아닌 리소스 형식의 사용자 지정 클레임을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9ea11-143">The following code example demonstrates how to create a custom claim with a primitive resource type and a custom claim with a non-primitive resource type.</span></span>  
  
 [!code-csharp[c_CustomClaim#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#0)]
 [!code-vb[c_CustomClaim#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#0)]  
  
## <a name="see-also"></a><span data-ttu-id="9ea11-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9ea11-144">See Also</span></span>  
 <xref:System.IdentityModel.Claims.Claim>  
 <xref:System.IdentityModel.Claims.Rights>  
 <xref:System.IdentityModel.Claims.ClaimTypes>  
 <xref:System.Runtime.Serialization.DataContractAttribute>  
 <xref:System.Runtime.Serialization.DataMemberAttribute>  
 [<span data-ttu-id="9ea11-145">ID 모델을 사용하여 클레임 및 권한 부여 관리</span><span class="sxs-lookup"><span data-stu-id="9ea11-145">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 [<span data-ttu-id="9ea11-146">ID 모델을 사용하여 클레임 및 권한 부여 관리</span><span class="sxs-lookup"><span data-stu-id="9ea11-146">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
