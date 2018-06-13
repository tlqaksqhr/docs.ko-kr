---
title: '방법: 세션이 필요한 서비스 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8a7613ef-0df9-47c3-b8dc-47f42cb1fd8b
ms.openlocfilehash: c7bcd0c08d00122df86d6682888907712f224a30
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33492725"
---
# <a name="how-to-create-a-service-that-requires-sessions"></a><span data-ttu-id="fea7b-102">방법: 세션이 필요한 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="fea7b-102">How to: Create a Service That Requires Sessions</span></span>
<span data-ttu-id="fea7b-103">세션은 콜백, 다중 홉 보안 및 클라이언트와 서비스 인스턴스 간의 연결과 같은 유용한 기능을 사용하는 둘 이상의 끝점 사이에서 공유 상태를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fea7b-103">Sessions create a shared state between two or more endpoints that enables useful features such as callbacks, multi-hop security, and associations between clients and service instances.</span></span> <span data-ttu-id="fea7b-104">Windows Communication Foundation (WCF) 응용 프로그램에서 세션에 대 한 자세한 내용은 참조 [를 사용 하 여 세션](../../../../docs/framework/wcf/using-sessions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fea7b-104">For more information about sessions in Windows Communication Foundation (WCF) applications, see [Using Sessions](../../../../docs/framework/wcf/using-sessions.md).</span></span>  
  
### <a name="to-specify-that-a-contract-require-its-binding-to-support-sessions"></a><span data-ttu-id="fea7b-105">계약에서 바인딩이 세션을 지원하도록 지정하려면</span><span class="sxs-lookup"><span data-stu-id="fea7b-105">To specify that a contract require its binding to support sessions</span></span>  
  
1.  <span data-ttu-id="fea7b-106">작업을 하나 이상 포함하는 서비스 계약을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fea7b-106">Create a service contract with at least one operation.</span></span> <span data-ttu-id="fea7b-107">서비스 계약을 만드는 방법의 예제를 보려면 [하는 방법: 서비스 계약 정의](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fea7b-107">For an example of how to create a service contract, see [How to: Define a Service Contract](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).</span></span>  
  
2.  <span data-ttu-id="fea7b-108"><xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType> 속성을 다음으로 설정하여 계약을 선언하는 <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType>를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="fea7b-108">Modify the <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType> that declares the contract by setting the <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType> property to either:</span></span>  
  
    -   <span data-ttu-id="fea7b-109">이 계약을 세션 내에서 실행해야 하는 경우, <xref:System.ServiceModel.SessionMode.Required?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="fea7b-109"><xref:System.ServiceModel.SessionMode.Required?displayProperty=nameWithType> if this contract must be run within a session.</span></span>  
  
    -   <span data-ttu-id="fea7b-110">이 계약을 세션 내에서 실행할 수 있는 경우, <xref:System.ServiceModel.SessionMode.Allowed?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="fea7b-110"><xref:System.ServiceModel.SessionMode.Allowed?displayProperty=nameWithType> if this contract can be run within a session.</span></span>  
  
    -   <span data-ttu-id="fea7b-111">이 계약을 세션 내에서 실행하지 않아야 하는 경우, <xref:System.ServiceModel.SessionMode.NotAllowed?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="fea7b-111"><xref:System.ServiceModel.SessionMode.NotAllowed?displayProperty=nameWithType> if this contract must not be run within a session.</span></span>  
  
3.  <span data-ttu-id="fea7b-112">세션을 지원하는 바인딩을 사용하도록 서비스 끝점을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="fea7b-112">Configure your service endpoint to use a binding that supports sessions.</span></span> <span data-ttu-id="fea7b-113">다음 구성 예제에서는 WS<xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>ReliableMessaging 세션을 지원하는 `-`을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fea7b-113">The following configuration example shows the use of the <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>, which supports a WS`-`ReliableMessaging session.</span></span>  
  
     [!code-xml[SCA.Session#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/hostapplication.exe.config#2)]   
  
## <a name="example"></a><span data-ttu-id="fea7b-114">예제</span><span class="sxs-lookup"><span data-stu-id="fea7b-114">Example</span></span>  
 <span data-ttu-id="fea7b-115">다음 예제 코드에서는 계약 수준 세션 요구 사항을 지정하고 구성 파일을 사용하여 <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType> 바인딩을 통해 해당 요구 사항을 지원하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fea7b-115">The following example code shows how to specify a contract-level session requirement and use a configuration file to support that requirement with the <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType> binding.</span></span>  
  
 [!code-csharp[SCA.Session#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/services.cs#1)] 
 [!code-vb[SCA.Session#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/sca.session/vb/services.vb#1)]      
 [!code-xml[SCA.Session#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/hostapplication.exe.config#2)]     
  
## <a name="see-also"></a><span data-ttu-id="fea7b-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fea7b-116">See Also</span></span>  
 <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType>  
 <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType>  
 <xref:System.ServiceModel.SessionMode?displayProperty=nameWithType>
