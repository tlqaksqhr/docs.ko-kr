---
title: '&lt;wsdlImporters&gt;'
ms.date: 03/30/2017
ms.assetid: 270c7f93-eab7-47b6-8b94-ac3f5b7f17e4
ms.openlocfilehash: 338d6fb9364847b13a8f1abe5671c508df99c255
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32767442"
---
# <a name="ltwsdlimportersgt"></a><span data-ttu-id="a7ba3-102">&lt;wsdlImporters&gt;</span><span class="sxs-lookup"><span data-stu-id="a7ba3-102">&lt;wsdlImporters&gt;</span></span>
<span data-ttu-id="a7ba3-103">이 구성 요소는 WS-Policy 첨부 파일과 함께 WSDL(웹 서비스 기술 언어) 1.1 메타데이터를 가져오는 모든 WSDL 가져오기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a7ba3-103">This configuration element specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span> <span data-ttu-id="a7ba3-104">각 자식 요소는 메타데이터를 가져오는 방법 및 그 정보를 계약 및 끝점 정보를 나타내는 다양한 클래스로 변환하는 방법을 지정하는 <`wsdlImporter`>입니다.</span><span class="sxs-lookup"><span data-stu-id="a7ba3-104">Each child element is a <`wsdlImporter`> that specifies the way to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="a7ba3-105">가져오기 오류를 공개하는 속성 및 계약과 끝점 정보를 가져오고, 가져오기 및 변환 프로세스와 관련된 형식 정보를 받을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7ba3-105">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="a7ba3-106">또한 정책 문서, WSDL 문서, WSDL 확장명 및 XML 스키마 문서에 대한 액세스를 제공하는 바인딩 정보와 속성의 가져오기도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="a7ba3-106">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7ba3-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a7ba3-107">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.MetadataElement>  
 <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>  
 <xref:System.ServiceModel.Description.MetadataImporter>  
 <xref:System.ServiceModel.Description.WsdlImporter>  
 [<span data-ttu-id="a7ba3-108">WCF 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="a7ba3-108">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [<span data-ttu-id="a7ba3-109">클라이언트</span><span class="sxs-lookup"><span data-stu-id="a7ba3-109">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
