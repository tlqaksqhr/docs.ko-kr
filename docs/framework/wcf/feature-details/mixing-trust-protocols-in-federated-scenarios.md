---
title: "페더레이션 시나리오에서 혼합 트러스트 프로토콜"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d7b5fee9-2246-4b09-b8d7-9e63cb817279
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 007dec81766423ea2826e98ae0b6b399a1508f11
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="mixing-trust-protocols-in-federated-scenarios"></a><span data-ttu-id="47796-102">페더레이션 시나리오에서 혼합 트러스트 프로토콜</span><span class="sxs-lookup"><span data-stu-id="47796-102">Mixing Trust Protocols in Federated Scenarios</span></span>
<span data-ttu-id="47796-103">페더레이션 클라이언트가 트러스트 버전이 다른 서비스 및 STS(보안 토큰 서비스)와 통신하는 시나리오가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47796-103">There may be scenarios in which federated clients communicate with a service and a Security Token Service (STS) that do not have the same trust version.</span></span> <span data-ttu-id="47796-104">서비스 WSDL에 STS와 버전이 다른 WS-Trust 요소가 있는 `RequestSecurityTokenTemplate` 어설션이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47796-104">The service WSDL can contain a `RequestSecurityTokenTemplate` assertion with WS-Trust elements that are of different versions than the STS.</span></span> <span data-ttu-id="47796-105">이 경우 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 클라이언트는 `RequestSecurityTokenTemplate`에서 수신한 WS-Trust 요소를 STS 트러스트 버전과 일치하도록 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="47796-105">In such cases, a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] client converts the WS-Trust elements received from the `RequestSecurityTokenTemplate` to match the STS trust version.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="47796-106">에서는 일치하지 않는 트러스트 버전을 표준 바인딩용으로만 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="47796-106"> handles mismatched trust versions only for standard bindings.</span></span> <span data-ttu-id="47796-107">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 인식되는 모든 표준 알고리즘 매개 변수가 표준 바인딩에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="47796-107">All standard algorithm parameters that are recognized by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] are part of the standard binding.</span></span> <span data-ttu-id="47796-108">이 항목에서는 서비스와 STS 간의 다양한 트러스트 설정을 사용한 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 동작에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="47796-108">This topic describes the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] behavior with various trust settings between the service and the STS.</span></span>  
  
## <a name="rp-feb-2005-and-sts-feb-2005"></a><span data-ttu-id="47796-109">RP 2005년 2월 및 STS 2005년 2월</span><span class="sxs-lookup"><span data-stu-id="47796-109">RP Feb 2005 and STS Feb 2005</span></span>  
 <span data-ttu-id="47796-110">RP(신뢰 당사자)에 대한 WSDL에서는 `RequestSecurityTokenTemplate` 섹션 내에 다음 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="47796-110">The WSDL for Relying Party (RP) contains the following elements within the `RequestSecurityTokenTemplate` section:</span></span>  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
 <span data-ttu-id="47796-111">클라이언트 구성 파일에는 매개 변수 목록이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="47796-111">The client configuration file contains a list of parameters.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="47796-112">에서는 클라이언트와 서비스 매개 변수를 구분할 수 없으므로 모든 매개 변수를 추가하고 이를 `RequestSecurityTokenTemplate`(RST)로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="47796-112"> cannot differentiate between the client and service parameters; it adds all the parameters and sends them in the `RequestSecurityTokenTemplate` (RST).</span></span>  
  
## <a name="rp-trust-13-and-sts-trust-13"></a><span data-ttu-id="47796-113">RP Trust 1.3 및 STS Trust 1.3</span><span class="sxs-lookup"><span data-stu-id="47796-113">RP Trust 1.3 and STS Trust 1.3</span></span>  
 <span data-ttu-id="47796-114">RP에 대한 WSDL에서는 `RequestSecurityTokenTemplate` 섹션 내에 다음 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="47796-114">The WSDL for RP contains the following elements within the `RequestSecurityTokenTemplate` section:</span></span>  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
-   `KeyWrapAlgorithm`  
  
 <span data-ttu-id="47796-115">클라이언트 구성 파일에는 RP에서 지정한 매개 변수를 래핑하는 `secondaryParameters` 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="47796-115">The client configuration file contains a `secondaryParameters` element that wraps the parameters specified by the RP.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="47796-116">에서는 `EncryptionAlgorithm`, `CanonicalizationAlgorithm` 및 `KeyWrapAlgorithm` 요소가 `SecondaryParameters` 요소 내에 있는 경우 RST의 최상위 요소에서 이러한 요소를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="47796-116"> removes the `EncryptionAlgorithm`, `CanonicalizationAlgorithm` and `KeyWrapAlgorithm` elements from the top-level element under the RST if these are present inside the `SecondaryParameters` element.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="47796-117">에서는 `SecondaryParameters` 요소를 수정되지 않은 나가는 RST에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="47796-117"> appends the `SecondaryParameters` element to the outgoing RST unmodified.</span></span>  
  
## <a name="rp-trust-feb-2005-and-sts-trust-13"></a><span data-ttu-id="47796-118">RP Trust 2005년 2월 및 STS Trust 1.3</span><span class="sxs-lookup"><span data-stu-id="47796-118">RP Trust Feb 2005 and STS Trust 1.3</span></span>  
 <span data-ttu-id="47796-119">RP에 대한 WSDL에서는 `RequestSecurityTokenTemplate` 섹션 내에 다음 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="47796-119">The WSDL for RP contains the following elements in the `RequestSecurityTokenTemplate` section:</span></span>  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
 <span data-ttu-id="47796-120">클라이언트 구성 파일에는 매개 변수 목록이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="47796-120">The client configuration file contains a list of parameters.</span></span>  
  
 <span data-ttu-id="47796-121">클라이언트 구성 파일에서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 서비스 및 클라이언트 매개 변수를 구분할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="47796-121">From the client configuration file, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] cannot differentiate between the service and client parameters.</span></span> <span data-ttu-id="47796-122">따라서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 모든 매개 변수를 Trust 버전 1.3 네임스페이스로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="47796-122">Therefore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] converts all the parameters to a Trust version 1.3 namespace.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="47796-123">에서는 `KeyType`, `KeySize` 및 `TokenType` 요소를 다음과 같이 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="47796-123"> handles the `KeyType`, `KeySize`, and `TokenType` elements as follows:</span></span>  
  
-   <span data-ttu-id="47796-124">WSDL을 다운로드하고, 바인딩을 만들고, RP 매개 변수에서 `KeyType`, `KeySize` 및 `TokenType`을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="47796-124">Download the WSDL, create the binding, and assign `KeyType`, `KeySize`, and `TokenType` from the RP parameters.</span></span> <span data-ttu-id="47796-125">그런 다음 클라이언트 구성 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="47796-125">The client configuration file is then generated.</span></span>  
  
-   <span data-ttu-id="47796-126">이제 클라이언트에서 구성 파일의 모든 매개 변수를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47796-126">The client can now change any parameter in the configuration file.</span></span>  
  
-   <span data-ttu-id="47796-127">런타임 동안 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 지정된 모든 매개 변수를 클라이언트 구성 파일의 `AdditionalTokenParameters` 섹션으로 복사합니다. 단, `KeyType`, `KeySize` 및 `TokenType` 매개 변수는 구성 파일 생성 동안에만 필요하므로 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="47796-127">During runtime, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] copies all parameters specified into the `AdditionalTokenParameters` section of the client configuration file except `KeyType`, `KeySize` and `TokenType`, because these parameters are accounted for during the configuration file generation.</span></span>  
  
## <a name="rp-trust-13-and-sts-trust-feb-2005"></a><span data-ttu-id="47796-128">RP Trust 1.3 및 STS Trust 2005년 2월</span><span class="sxs-lookup"><span data-stu-id="47796-128">RP Trust 1.3 and STS Trust Feb 2005</span></span>  
 <span data-ttu-id="47796-129">RP에 대한 WSDL에서는 `RequestSecurityTokenTemplate` 섹션 내에 다음 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="47796-129">The WSDL for RP contains the following elements in the `RequestSecurityTokenTemplate` section:</span></span>  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
-   `KeyWrapAlgorithm`  
  
 <span data-ttu-id="47796-130">클라이언트 구성 파일에는 RP에서 지정한 매개 변수를 래핑하는 `secondaryParamters` 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="47796-130">The client configuration file contains a `secondaryParamters` element that wraps the parameters specified by the RP.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="47796-131">에서는 `SecondaryParameters` 섹션 내의 지정된 모든 매개 변수를 최상위 RST 요소로 복사하지만 2005 WS-Trust 네임스페이스로 변환하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47796-131"> copies all the parameters specified within the `SecondaryParameters` section to the top-level RST element, but does not convert them to the 2005 WS-Trust namespace.</span></span>
