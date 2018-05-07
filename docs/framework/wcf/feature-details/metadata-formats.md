---
title: 메타데이터 형식
ms.date: 03/30/2017
ms.assetid: baad1e68-28fc-4a6a-8a43-75e47e7fa871
ms.openlocfilehash: a3c6b1f551d1bff8c68a91f33e62df289d2078cc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="metadata-formats"></a>메타데이터 형식
Windows Communication Foundation (WCF)는 다음 표에 메타 데이터 형식을 지원합니다.  
  
## <a name="metadata-specifications-and-usage"></a>메타데이터 사양 및 사용  
  
|프로토콜|사양 및 사용|  
|--------------|-----------------------------|  
|WSDL 1.1|[웹 서비스 기술 언어 (WSDL) 1.1](http://go.microsoft.com/fwlink/?LinkId=94859)<br /><br /> WCF는 서비스를 설명 하기 위해 WSDL 웹 서비스 설명 언어 ()를 사용 합니다.|  
|XML 스키마|[XML 스키마 2 부: Datatypes Second Edition](http://go.microsoft.com/fwlink/?LinkId=94861) 및 [XML 스키마 1 부: 구조 Second Edition](http://go.microsoft.com/fwlink/?LinkId=94862)<br /><br /> WCF는 메시지에 사용 되는 데이터 형식을 설명 하는 XML 스키마를 사용 합니다.|  
|WS Policy|[웹 서비스 정책 1.2-프레임 워크 (Ws-policy)](http://go.microsoft.com/fwlink/?LinkId=94864)<br /><br /> [웹 서비스 정책 1.5-프레임 워크](http://go.microsoft.com/fwlink/?LinkId=94865)<br /><br /> WCF를 사용 하 여 Ws-policy 1.2 또는 1.5 사양을 도메인별 어설션과 함께 서비스 요구 사항 및 기능에 설명 합니다.|  
|WS Policy 첨부 파일|[웹 서비스 정책 1.2-첨부 파일 (Ws-policyattachment)](http://go.microsoft.com/fwlink/?LinkId=94866)<br /><br /> WCF는 WSDL에서 다양 한 범위의 정책 식을 연결할 WS Policy 첨부 파일을 구현 합니다.|  
|WS Metadata Exchange|[웹 서비스 메타 데이터 교환 (Ws-metadataexchange) 버전 1.1](http://go.microsoft.com/fwlink/?LinkId=94868)<br /><br /> WCF를 XML 스키마, WSDL 및 Ws-policy를 검색 한 Ws-metadataexchange를 구현 합니다.|  
|WSDL에 대한 WS-Addressing 바인딩|[Web Services Addressing 1.0-WSDL 바인딩](http://go.microsoft.com/fwlink/?LinkId=94869)<br /><br /> WCF는 WSDL에서 주소 지정 정보를 연결 하는 WSDL에 대 한 Ws-addressing 바인딩을 구현 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [시스템 제공 상호 운용성 바인딩에서 지원하는 웹 서비스 프로토콜](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md)  
 [WSDL 및 정책](../../../../docs/framework/wcf/feature-details/wsdl-and-policy.md)
