---
title: '방법: 권한을 부여하는 동안 메타데이터 요청 허용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- allowing metadata requests while authorizing [WCF]
ms.assetid: 90cec34f-b619-452b-a056-8b1c0de49d05
ms.openlocfilehash: 2f855080cf3ba4cee08470af77c52945e47a2ec4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33489637"
---
# <a name="how-to-allow-metadata-requests-while-authorizing"></a><span data-ttu-id="568b9-102">방법: 권한을 부여하는 동안 메타데이터 요청 허용</span><span class="sxs-lookup"><span data-stu-id="568b9-102">How To: Allow Metadata Requests While Authorizing</span></span>
<span data-ttu-id="568b9-103">사용자 지정 인증을 수행하는 동안 메타데이터를 처리하도록 요청을 허용해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="568b9-103">During custom authorization, it may be necessary to allow a request for metadata to be processed.</span></span> <span data-ttu-id="568b9-104">다음 항목에서는 이러한 요청의 유효성을 검사하는 단계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="568b9-104">The following topic walks through the steps to validate such a request.</span></span>  
  
 <span data-ttu-id="568b9-105">Windows Communication Foundation (WCF) 권한 부여에 대 한 자세한 내용은 참조 [권한 부여](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="568b9-105">For more information about Windows Communication Foundation (WCF) authorization, see [Authorization](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).</span></span>  
  
### <a name="to-allow-metadata-requests-during-authorization"></a><span data-ttu-id="568b9-106">권한을 부여하는 동안 메타데이터 요청을 허용하려면</span><span class="sxs-lookup"><span data-stu-id="568b9-106">To allow metadata requests during authorization</span></span>  
  
1.  <span data-ttu-id="568b9-107"><xref:System.ServiceModel.ServiceAuthorizationManager> 클래스의 확장을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="568b9-107">Create an extension of the <xref:System.ServiceModel.ServiceAuthorizationManager> class.</span></span>  
  
2.  <span data-ttu-id="568b9-108"><xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="568b9-108">Override the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method.</span></span> <span data-ttu-id="568b9-109">메서드는 권한 부여가 허용되는지 여부에 따라 `true` 또는 `false`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="568b9-109">The method returns `true` or `false` depending on whether authorization is allowed.</span></span> <span data-ttu-id="568b9-110">현재 프로시저에 대한 정보는 매개 변수로서 메서드에 전달된 <xref:System.ServiceModel.OperationContext>에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="568b9-110">Information about the current procedure is found in the <xref:System.ServiceModel.OperationContext> passed as a parameter to the method.</span></span>  
  
3.  <span data-ttu-id="568b9-111">재정의하는 동안 다음 예제에서처럼 계약 이름, 네임스페이스 및 작업을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="568b9-111">In the override, check the contract name, namespace, and the action as shown in the following example.</span></span> <span data-ttu-id="568b9-112">조건이 올바른 경우 `true.`가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="568b9-112">If the conditions are valid, then return `true.`</span></span>  
  
4.  <span data-ttu-id="568b9-113">확장성 지점을 사용하여 클래스를 채택합니다.</span><span class="sxs-lookup"><span data-stu-id="568b9-113">Use the extensibility point to employ the class.</span></span> <span data-ttu-id="568b9-114">자세한 내용은 참조 [하는 방법: 서비스에 대 한 사용자 지정 권한 부여 관리자 만들기](../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="568b9-114">For more information, see [How to: Create a Custom Authorization Manager for a Service](../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="568b9-115">예제</span><span class="sxs-lookup"><span data-stu-id="568b9-115">Example</span></span>  
 <span data-ttu-id="568b9-116">다음 예제에서는 <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> 메서드의 재정의를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="568b9-116">The following example shows an override of the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method.</span></span>  
  
 [!code-csharp[C_HowtoCheckForMexRequestsInAuthorization#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtocheckformexrequestsinauthorization/cs/source.cs#1)]
 [!code-vb[C_HowtoCheckForMexRequestsInAuthorization#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtocheckformexrequestsinauthorization/vb/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="568b9-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="568b9-117">See Also</span></span>  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
 [<span data-ttu-id="568b9-118">권한 부여</span><span class="sxs-lookup"><span data-stu-id="568b9-118">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
 [<span data-ttu-id="568b9-119">ID 모델을 사용하여 클레임 및 권한 부여 관리</span><span class="sxs-lookup"><span data-stu-id="568b9-119">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
