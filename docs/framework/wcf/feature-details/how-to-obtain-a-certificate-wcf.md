---
title: '방법: 인증서 가져오기(WCF)'
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], obtaining
ms.assetid: d53762fd-15ea-42dc-b0ea-6a6597aa23f7
ms.openlocfilehash: 368401d91aa2a83110631d583660d6ccebf8d4fc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33491509"
---
# <a name="how-to-obtain-a-certificate-wcf"></a><span data-ttu-id="d3046-102">방법: 인증서 가져오기(WCF)</span><span class="sxs-lookup"><span data-stu-id="d3046-102">How to: Obtain a Certificate (WCF)</span></span>
<span data-ttu-id="d3046-103">Windows Communication Foundation (WCF) 중 하나를 사용 하는의 기능을 사용 하려면 X.509 인증서 먼저 인증서를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="d3046-103">To use any of the Windows Communication Foundation (WCF) features of that use X.509 certificates, you just first obtain certificates.</span></span>  
  
### <a name="to-obtain-an-x509-certificate"></a><span data-ttu-id="d3046-104">X.509 인증서를 받으려면</span><span class="sxs-lookup"><span data-stu-id="d3046-104">To obtain an X.509 certificate</span></span>  
  
1.  <span data-ttu-id="d3046-105">다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d3046-105">Choose one of the following:</span></span>  
  
    -   <span data-ttu-id="d3046-106">VeriSign, Inc, 같은 인증 기관에서 인증서를 구입합니다.</span><span class="sxs-lookup"><span data-stu-id="d3046-106">Purchase a certificate from a certification authority, such as VeriSign, Inc.</span></span>  
  
    -   <span data-ttu-id="d3046-107">자체 인증서 서비스를 설정하고 인증 기관이 인증서에 서명하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3046-107">Set up your own certificate service and have a certification authority sign the certificates.</span></span> [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]<span data-ttu-id="d3046-108">, Windows 2000 Server, Windows 2000 Server Datacenter 및 Windows 2000 Datacenter Server에는 모두 PKI(공개 키 인프라)를 지원하는 인증서 서비스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3046-108">, Windows 2000 Server, Windows 2000 Server Datacenter, and Windows 2000 Datacenter Server all include certificate services that support public key infrastructure (PKI).</span></span> <span data-ttu-id="d3046-109">Windows Server 2008에서 사용 하 여는 [Active Directory 인증서 서비스](http://go.microsoft.com/fwlink/?LinkID=153483) 인증 기관 관리 하기 위해 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="d3046-109">In Windows Server 2008, use the [Active Directory Certificate Services](http://go.microsoft.com/fwlink/?LinkID=153483) role to manage a certification authority.</span></span>  
  
    -   <span data-ttu-id="d3046-110">자체 인증서 서비스를 설정하고 인증서가 서명되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3046-110">Set up your own certificate service and do not have the certificates signed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d3046-111">어떤 방법을 선택하든 관계없이 X.509 인증서를 포함하는 SOAP 요청의 수신자는 X.509 인증서를 신뢰해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3046-111">Whichever approach you take, the recipient of the SOAP request that contains the X.509 certificate must trust the X.509 certificate.</span></span> <span data-ttu-id="d3046-112">이는 X.509 인증서나 인증서 체인의 발급자가 신뢰된 사용자 인증서에 있고 X.509 인증서가 신뢰되지 않은 인증서 저장소에 없음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="d3046-112">This means that the X.509 certificate or an issuer in the certificate chain is in the Trusted People certificate store and that the X.509 certificate is not in the Untrusted Certificates store.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3046-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d3046-113">See Also</span></span>  
 [<span data-ttu-id="d3046-114">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="d3046-114">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="d3046-115">방법: 개발 중 사용할 임시 인증서 만들기</span><span class="sxs-lookup"><span data-stu-id="d3046-115">How to: Create Temporary Certificates for Use During Development</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)
