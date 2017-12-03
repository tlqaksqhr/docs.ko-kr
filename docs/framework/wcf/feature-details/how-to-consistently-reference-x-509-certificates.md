---
title: "방법: 일관성 있게 X.509 인증서 참조"
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
helpviewer_keywords: certificates [WCF], referencing X.509 certificates
ms.assetid: a6de1c63-e450-4640-ad08-ad7302dbfbfc
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e92b3b4950e0a2edecc9a1f954a9f2959595c4e3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-consistently-reference-x509-certificates"></a><span data-ttu-id="c36a7-102">방법: 일관성 있게 X.509 인증서 참조</span><span class="sxs-lookup"><span data-stu-id="c36a7-102">How to: Consistently Reference X.509 Certificates</span></span>
<span data-ttu-id="c36a7-103">인증서의 해시, 발급자와 일련 번호 또는 SKI(주체 키 식별자) 등의 다양한 방법으로 인증서를 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c36a7-103">You can identify a certificate in several ways: by the hash of the certificate, by the issuer and serial number, or by the subject key identifier (SKI).</span></span> <span data-ttu-id="c36a7-104">SKI는 인증서 주체 공개 키의 고유 ID를 제공하며 XML 디지털 서명을 사용할 때 주로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c36a7-104">The SKI provides a unique identification for the certificate's subject public key and is often used when working with XML digital signing.</span></span> <span data-ttu-id="c36a7-105">SKI 값은 일반적으로 X.509 인증서의 일부는 *X.509 인정 서 확장*합니다.</span><span class="sxs-lookup"><span data-stu-id="c36a7-105">The SKI value is usually part of the X.509 certificate as an *X.509 certificate extension*.</span></span> [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="c36a7-106">에 기본 *참조 스타일* 발급자와 일련 번호를 사용 하는 인증서에 SKI 확장이 없는 경우.</span><span class="sxs-lookup"><span data-stu-id="c36a7-106"> has a default *referencing style* that uses the issuer and serial number if the SKI extension is missing from the certificate.</span></span> <span data-ttu-id="c36a7-107">인증서에 SKI 확장이 있는 경우 기본 참조 스타일에서는 SKI를 사용하여 인증서를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="c36a7-107">If the certificate contains the SKI extension, the default referencing style uses the SKI to point to the certificate.</span></span> <span data-ttu-id="c36a7-108">응용 프로그램을 개발하는 도중에 SKI 확장을 사용하지 않는 인증서에서 SKI 확장을 사용하는 인증서로 전환하는 경우 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 생성된 메시지에 사용되는 참조 스타일도 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="c36a7-108">If mid-way through development of an application, you switch from using certificates that do not use the SKI extension to certificates that use the SKI extension, the referencing style used in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-generated messages also changes.</span></span>  
  
 <span data-ttu-id="c36a7-109">SKI 확장의 존재 여부에 관계없이 일관성 있는 참조 스타일을 사용해야 하는 경우에는 다음 코드처럼 원하는 참조 스타일을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c36a7-109">If a consistent referencing style is required regardless of SKI extension presence, it is possible to configure the desired referencing style as shown in the following code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c36a7-110">예제</span><span class="sxs-lookup"><span data-stu-id="c36a7-110">Example</span></span>  
 <span data-ttu-id="c36a7-111">다음 예제에서는 일관성 있는 단일 참조 스타일(발급자 이름과 일련 번호)을 사용하는 사용자 지정 보안 바인딩 요소를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c36a7-111">The following example creates a custom security binding element that uses a single consistent referencing style, the issuer name and serial number.</span></span>  
  
 [!code-csharp[c_ReferencingCertificatesConsistently#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_referencingcertificatesconsistently/cs/source.cs#1)]
 [!code-vb[c_ReferencingCertificatesConsistently#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_referencingcertificatesconsistently/vb/source.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c36a7-112">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="c36a7-112">Compiling the Code</span></span>  
 <span data-ttu-id="c36a7-113">코드를 컴파일하려면 다음 네임스페이스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c36a7-113">The following namespaces are required to compile the code:</span></span>  
  
-   <xref:System>  
  
-   <xref:System.ServiceModel>  
  
-   <xref:System.ServiceModel.Channels>  
  
-   <xref:System.ServiceModel.Security.Tokens>  
  
## <a name="see-also"></a><span data-ttu-id="c36a7-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c36a7-114">See Also</span></span>  
 [<span data-ttu-id="c36a7-115">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="c36a7-115">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
