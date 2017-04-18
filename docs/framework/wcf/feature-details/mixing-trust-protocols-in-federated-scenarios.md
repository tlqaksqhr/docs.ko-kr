---
title: "페더레이션 시나리오에서 혼합 트러스트 프로토콜 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d7b5fee9-2246-4b09-b8d7-9e63cb817279
caps.latest.revision: 7
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# 페더레이션 시나리오에서 혼합 트러스트 프로토콜
페더레이션 클라이언트가 트러스트 버전이 다른 서비스 및 STS\(보안 토큰 서비스\)와 통신하는 시나리오가 있을 수 있습니다.  서비스 WSDL에 STS와 버전이 다른 WS\-Trust 요소가 있는 `RequestSecurityTokenTemplate` 어설션이 포함될 수 있습니다.  이 경우 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 클라이언트는 `RequestSecurityTokenTemplate`에서 수신한 WS\-Trust 요소를 STS 트러스트 버전과 일치하도록 변환합니다.  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 일치하지 않는 트러스트 버전을 표준 바인딩용으로만 처리합니다.  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 인식되는 모든 표준 알고리즘 매개 변수가 표준 바인딩에 포함됩니다.  이 항목에서는 서비스와 STS 간의 다양한 트러스트 설정을 사용한 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 동작에 대해 설명합니다.  
  
## RP 2005년 2월 및 STS 2005년 2월  
 RP\(신뢰 당사자\)에 대한 WSDL에서는 `RequestSecurityTokenTemplate` 섹션 내에 다음 요소를 포함합니다.  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
 클라이언트 구성 파일에는 매개 변수 목록이 포함됩니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 클라이언트와 서비스 매개 변수를 구분할 수 없으므로 모든 매개 변수를 추가하고 이를 `RequestSecurityTokenTemplate`\(RST\)로 보냅니다.  
  
## RP Trust 1.3 및 STS Trust 1.3  
 RP에 대한 WSDL에서는 `RequestSecurityTokenTemplate` 섹션 내에 다음 요소를 포함합니다.  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
-   `KeyWrapAlgorithm`  
  
 클라이언트 구성 파일에는 RP에서 지정한 매개 변수를 래핑하는 `secondaryParameters` 요소가 포함됩니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 `EncryptionAlgorithm`, `CanonicalizationAlgorithm` 및 `KeyWrapAlgorithm` 요소가 `SecondaryParameters` 요소 내에 있는 경우 RST의 최상위 요소에서 이러한 요소를 제거합니다.  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 `SecondaryParameters` 요소를 수정되지 않은 나가는 RST에 추가합니다.  
  
## RP Trust 2005년 2월 및 STS Trust 1.3  
 RP에 대한 WSDL에서는 `RequestSecurityTokenTemplate` 섹션 내에 다음 요소를 포함합니다.  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
 클라이언트 구성 파일에는 매개 변수 목록이 포함됩니다.  
  
 클라이언트 구성 파일에서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 서비스 및 클라이언트 매개 변수를 구분할 수 없습니다.  따라서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 모든 매개 변수를 Trust 버전 1.3 네임스페이스로 변환합니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 `KeyType`, `KeySize` 및 `TokenType` 요소를 다음과 같이 처리합니다.  
  
-   WSDL을 다운로드하고, 바인딩을 만들고, RP 매개 변수에서 `KeyType`, `KeySize` 및 `TokenType`을 할당합니다.  그런 다음 클라이언트 구성 파일이 생성됩니다.  
  
-   이제 클라이언트에서 구성 파일의 모든 매개 변수를 수정할 수 있습니다.  
  
-   런타임 동안 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 지정된 모든 매개 변수를 클라이언트 구성 파일의 `AdditionalTokenParameters` 섹션으로 복사합니다. 단, `KeyType`, `KeySize` 및 `TokenType` 매개 변수는 구성 파일 생성 동안에만 필요하므로 제외됩니다.  
  
## RP Trust 1.3 및 STS Trust 2005년 2월  
 RP에 대한 WSDL에서는 `RequestSecurityTokenTemplate` 섹션 내에 다음 요소를 포함합니다.  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
-   `KeyWrapAlgorithm`  
  
 클라이언트 구성 파일에는 RP에서 지정한 매개 변수를 래핑하는 `secondaryParamters` 요소가 포함됩니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 `SecondaryParameters` 섹션 내의 지정된 모든 매개 변수를 최상위 RST 요소로 복사하지만 2005 WS\-Trust 네임스페이스로 변환하지는 않습니다.