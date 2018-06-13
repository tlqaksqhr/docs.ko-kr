---
title: '방법: 일관성 있게 X.509 인증서 참조'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- certificates [WCF], referencing X.509 certificates
ms.assetid: a6de1c63-e450-4640-ad08-ad7302dbfbfc
ms.openlocfilehash: efc4fb399224de7f03c6bffb606178184de1d467
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33489387"
---
# <a name="how-to-consistently-reference-x509-certificates"></a><span data-ttu-id="b7afa-102">방법: 일관성 있게 X.509 인증서 참조</span><span class="sxs-lookup"><span data-stu-id="b7afa-102">How to: Consistently Reference X.509 Certificates</span></span>
<span data-ttu-id="b7afa-103">인증서의 해시, 발급자와 일련 번호 또는 SKI(주체 키 식별자) 등의 다양한 방법으로 인증서를 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7afa-103">You can identify a certificate in several ways: by the hash of the certificate, by the issuer and serial number, or by the subject key identifier (SKI).</span></span> <span data-ttu-id="b7afa-104">SKI는 인증서 주체 공개 키의 고유 ID를 제공하며 XML 디지털 서명을 사용할 때 주로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7afa-104">The SKI provides a unique identification for the certificate's subject public key and is often used when working with XML digital signing.</span></span> <span data-ttu-id="b7afa-105">SKI 값은 일반적으로 X.509 인증서의 일부는 *X.509 인정 서 확장*합니다.</span><span class="sxs-lookup"><span data-stu-id="b7afa-105">The SKI value is usually part of the X.509 certificate as an *X.509 certificate extension*.</span></span> <span data-ttu-id="b7afa-106">Windows Communication Foundation (WCF)에 기본 *참조 스타일* 발급자와 일련 번호를 사용 하는 인증서에 SKI 확장이 없는 경우.</span><span class="sxs-lookup"><span data-stu-id="b7afa-106">Windows Communication Foundation (WCF) has a default *referencing style* that uses the issuer and serial number if the SKI extension is missing from the certificate.</span></span> <span data-ttu-id="b7afa-107">인증서에 SKI 확장이 있는 경우 기본 참조 스타일에서는 SKI를 사용하여 인증서를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="b7afa-107">If the certificate contains the SKI extension, the default referencing style uses the SKI to point to the certificate.</span></span> <span data-ttu-id="b7afa-108">중간 방식으로 응용 프로그램을 개발 하는 경우을 전환 하는 SKI 확장을 사용 하는 인증서에 SKI 확장을 사용 하지 않는 인증서를 사용 하 여 WCF에서 생성 된 메시지에 사용 되는 참조 스타일도 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7afa-108">If mid-way through development of an application, you switch from using certificates that do not use the SKI extension to certificates that use the SKI extension, the referencing style used in WCF-generated messages also changes.</span></span>  
  
 <span data-ttu-id="b7afa-109">SKI 확장의 존재 여부에 관계없이 일관성 있는 참조 스타일을 사용해야 하는 경우에는 다음 코드처럼 원하는 참조 스타일을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7afa-109">If a consistent referencing style is required regardless of SKI extension presence, it is possible to configure the desired referencing style as shown in the following code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7afa-110">예제</span><span class="sxs-lookup"><span data-stu-id="b7afa-110">Example</span></span>  
 <span data-ttu-id="b7afa-111">다음 예제에서는 일관성 있는 단일 참조 스타일(발급자 이름과 일련 번호)을 사용하는 사용자 지정 보안 바인딩 요소를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b7afa-111">The following example creates a custom security binding element that uses a single consistent referencing style, the issuer name and serial number.</span></span>  
  
 [!code-csharp[c_ReferencingCertificatesConsistently#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_referencingcertificatesconsistently/cs/source.cs#1)]
 [!code-vb[c_ReferencingCertificatesConsistently#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_referencingcertificatesconsistently/vb/source.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b7afa-112">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="b7afa-112">Compiling the Code</span></span>  
 <span data-ttu-id="b7afa-113">코드를 컴파일하려면 다음 네임스페이스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b7afa-113">The following namespaces are required to compile the code:</span></span>  
  
-   <xref:System>  
  
-   <xref:System.ServiceModel>  
  
-   <xref:System.ServiceModel.Channels>  
  
-   <xref:System.ServiceModel.Security.Tokens>  
  
## <a name="see-also"></a><span data-ttu-id="b7afa-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b7afa-114">See Also</span></span>  
 [<span data-ttu-id="b7afa-115">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="b7afa-115">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
