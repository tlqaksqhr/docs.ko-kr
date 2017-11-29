---
title: "방법: 지정된 인증 모드에 대한 SecurityBindingElement 만들기"
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
ms.assetid: a7c7747a-5b8c-463f-8493-7266dac75066
caps.latest.revision: "9"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 658eaf3469e0be179c78d9963687e6de9cb7fc00
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-securitybindingelement-for-a-specified-authentication-mode"></a><span data-ttu-id="02d07-102">방법: 지정된 인증 모드에 대한 SecurityBindingElement 만들기</span><span class="sxs-lookup"><span data-stu-id="02d07-102">How to: Create a SecurityBindingElement for a Specified Authentication Mode</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="02d07-103">에는 클라이언트와 서버가 서로를 인증하는 데 사용되는 모드가 몇 가지 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02d07-103"> provides several modes by which clients and services authenticate to one another.</span></span> <span data-ttu-id="02d07-104"><xref:System.ServiceModel.Channels.SecurityBindingElement> 클래스에 static 메서드를 사용하거나 다음 예제처럼 구성을 통해 이러한 인증 모드의 보안 바인딩 요소를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02d07-104">You can create security binding elements for these authentication modes by using static methods on the <xref:System.ServiceModel.Channels.SecurityBindingElement> class or through configuration, as shown in the following example.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="02d07-105">18 가지의 인증 모드 참조 [SecurityBindingElement 인증 모드](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="02d07-105"> the 18 authentication modes, see [SecurityBindingElement Authentication Modes](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="02d07-106">예제</span><span class="sxs-lookup"><span data-stu-id="02d07-106">Example</span></span>  
 <span data-ttu-id="02d07-107">다음 코드 예제에서는 다양한 인증 모드의 바인딩을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="02d07-107">The following code example shows methods for creating bindings for the various authentication modes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="02d07-108"><xref:System.ServiceModel.Channels.SecurityBindingElement> 개체의 인스턴스를 만들면 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.KeyType%2A> 및 <xref:System.ServiceModel.Channels.SecurityBindingElement.MessageSecurityVersion%2A> 등의 여러 속성을 변경할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02d07-108">Once an instance of the <xref:System.ServiceModel.Channels.SecurityBindingElement> object is created, a number of properties are immutable, such as <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.KeyType%2A> and <xref:System.ServiceModel.Channels.SecurityBindingElement.MessageSecurityVersion%2A>.</span></span> <span data-ttu-id="02d07-109">이러한 속성에서 `set`을 호출해도 해당 속성은 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="02d07-109">Calling `set` on such properties does not change them.</span></span>  
  
 [!code-csharp[c_CustomBindingsAuthMode#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombindingsauthmode/cs/source.cs#2)]
 [!code-vb[c_CustomBindingsAuthMode#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_custombindingsauthmode/vb/source.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="02d07-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="02d07-110">See Also</span></span>  
 [<span data-ttu-id="02d07-111">SecurityBindingElement 인증 모드</span><span class="sxs-lookup"><span data-stu-id="02d07-111">SecurityBindingElement Authentication Modes</span></span>](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md)  
 [<span data-ttu-id="02d07-112">방법: SecurityBindingElement를 사용 하 여 사용자 지정 바인딩을 만들려면</span><span class="sxs-lookup"><span data-stu-id="02d07-112">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
