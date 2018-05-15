---
title: WS-I Basic Profile 1.1 상호 운용할 수 있는 서비스 만들기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- configuration [WCF], interoperable services
ms.assetid: 91b70a21-8f5c-4679-808c-2ed5fa6b2013
ms.openlocfilehash: aa76a6633ef86a908e00bb9dcb1b16eefe35c12d
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="creating-ws-i-basic-profile-11-interoperable-services"></a><span data-ttu-id="2ffc6-102">WS-I Basic Profile 1.1 상호 운용할 수 있는 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="2ffc6-102">Creating WS-I Basic Profile 1.1 Interoperable Services</span></span>
<span data-ttu-id="2ffc6-103">상호 운용 가능 하도록 WCF 서비스 끝점을 구성 하려면 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] 웹 서비스 클라이언트:</span><span class="sxs-lookup"><span data-stu-id="2ffc6-103">To configure a WCF service endpoint to be interoperable with [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] Web service clients:</span></span>  
  
-   <span data-ttu-id="2ffc6-104"><xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> 형식을 서비스 끝점의 바인딩 형식으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2ffc6-104">Use the <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> type as the binding type for your service endpoint.</span></span>  
  
-   <span data-ttu-id="2ffc6-105">서비스 끝점에서 콜백 및 세션 계약 기능이나 트랜잭션 동작을 사용하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ffc6-105">Do not use callback and session contract features or transaction behaviors on your service endpoint</span></span>  
  
 <span data-ttu-id="2ffc6-106">바인딩에서 HTTPS 및 전송 수준 클라이언트 인증에 대한 지원을 선택적으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ffc6-106">You can optionally enable support for HTTPS and transport-level client authentication on the binding.</span></span>  
  
 <span data-ttu-id="2ffc6-107"><xref:System.ServiceModel.BasicHttpBinding> 클래스의 다음 기능에는 WS-I Basic Profile 1.1 이상의 기능이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2ffc6-107">The following features of the <xref:System.ServiceModel.BasicHttpBinding> class require functionality beyond WS-I Basic Profile 1.1:</span></span>  
  
-   <span data-ttu-id="2ffc6-108"><xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType> 속성을 사용하여 제어하는 MTOM(Message Transmission Optimization Mechanism) 메시지 인코딩입니다.</span><span class="sxs-lookup"><span data-stu-id="2ffc6-108">Message Transmission Optimization Mechanism (MTOM) message encoding controlled by the <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="2ffc6-109">MTOM을 사용하지 않으려면 이 속성을 기본값인 <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType>로 둡니다.</span><span class="sxs-lookup"><span data-stu-id="2ffc6-109">Leave  this property at its default value, which is <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType> to not use MTOM.</span></span>  
  
-   <span data-ttu-id="2ffc6-110"><xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> 값을 사용하여 제어하는 메시지 보안에서는 WS-I Basic Security Profile 1.0과 호환되는 WS-Security를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="2ffc6-110">Message security controlled by the <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> value provides WS-Security support compliant with WS-I Basic Security Profile 1.0.</span></span> <span data-ttu-id="2ffc6-111">WS-Security를 사용하지 않으려면 이 속성을 기본값인 <xref:System.ServiceModel.SecurityMode.Transport?displayProperty=nameWithType>로 둡니다.</span><span class="sxs-lookup"><span data-stu-id="2ffc6-111">Leave this property at its default value, which is <xref:System.ServiceModel.SecurityMode.Transport?displayProperty=nameWithType> to not use WS-Security.</span></span>  
  
 <span data-ttu-id="2ffc6-112">WCF 서비스에 대 한 메타 데이터를 사용할 수 있도록 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], 웹 서비스 클라이언트 생성 도구를 사용 하 여: [웹 서비스 설명 언어 도구 (Wsdl.exe)](http://msdn.microsoft.com/library/b9210348-8bc2-4367-8c91-d1a04b403e88), [웹 서비스 검색 도구 (Disco.exe)](http://msdn.microsoft.com/library/acd88078-c581-42bc-94ca-6633e2851979), 및 `Add Web Reference` Visual Studio에서 기능; 메타 데이터 게시를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ffc6-112">To make the metadata for a WCF service available to [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], use the Web service client generation tools: [Web Services Description Language Tool (Wsdl.exe)](http://msdn.microsoft.com/library/b9210348-8bc2-4367-8c91-d1a04b403e88), [Web Services Discovery Tool (Disco.exe)](http://msdn.microsoft.com/library/acd88078-c581-42bc-94ca-6633e2851979), and the `Add Web Reference` feature in Visual Studio; you must enable metadata publication.</span></span> <span data-ttu-id="2ffc6-113">자세한 내용은 참조 [메타 데이터 끝점 게시](../../../docs/framework/wcf/publishing-metadata-endpoints.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2ffc6-113">For more information, see [Publishing Metadata Endpoints](../../../docs/framework/wcf/publishing-metadata-endpoints.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ffc6-114">예제</span><span class="sxs-lookup"><span data-stu-id="2ffc6-114">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="2ffc6-115">설명</span><span class="sxs-lookup"><span data-stu-id="2ffc6-115">Description</span></span>  
 <span data-ttu-id="2ffc6-116">다음 예제 코드와 호환 되는 WCF 끝점을 추가 하는 방법을 보여 줍니다 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] 웹 서비스 클라이언트 코드에서 또는 구성 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ffc6-116">The following example code demonstrates how to add a WCF endpoint that is compatible with [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] Web service clients in code and, alternatively, in a configuration file.</span></span>  
  
### <a name="code"></a><span data-ttu-id="2ffc6-117">코드</span><span class="sxs-lookup"><span data-stu-id="2ffc6-117">Code</span></span>  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)]
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)]  
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]  
  
## <a name="see-also"></a><span data-ttu-id="2ffc6-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2ffc6-118">See Also</span></span>  
 [<span data-ttu-id="2ffc6-119">ASP.NET 웹 서비스와의 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="2ffc6-119">Interoperability with ASP.NET Web Services</span></span>](../../../docs/framework/wcf/feature-details/interop-with-aspnet-web-services.md)
