---
title: "기본 프로그래밍 수명 주기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: service creation [WCF]
ms.assetid: 7cf21bfe-23bd-46aa-8033-609f851dbf76
caps.latest.revision: "36"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f17b37b77c157f1ce3d5ee40fd6464ab378039d5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="basic-programming-lifecycle"></a>기본 프로그래밍 수명 주기
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)]를 사용하면 응용 프로그램들이 같은 컴퓨터에 있든지, 인터넷을 통해 연결되어 있든지 아니면 서로 다른 응용 프로그램 플랫폼에 있든지 상관없이 통신할 수 있습니다. 이 항목에서는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 응용 프로그램을 빌드하는 데 필요한 작업에 대해 간략하게 설명합니다. 작업 샘플 응용 프로그램에 대 한 참조 [초보자를 위한 자습서](../../../docs/framework/wcf/getting-started-tutorial.md)합니다.  
  
## <a name="the-basic-tasks"></a>기본 작업  
 수행할 기본 작업 순서는 다음과 같습니다.  
  
1.  서비스 계약을 정의합니다. 서비스 계약은 서비스 서명, 서비스 교환 날짜 및 계약에 필요한 기타 데이터를 지정합니다. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][서비스 계약을 디자인](../../../docs/framework/wcf/designing-service-contracts.md)합니다.  
  
2.  계약을 구현합니다. 서비스 계약을 구현하려면 계약을 구현하는 클래스를 만들고 런타임에 필요한 사용자 지정 동작을 지정합니다. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][서비스 계약 구현](../../../docs/framework/wcf/implementing-service-contracts.md)합니다.  
  
3.  끝점 및 기타 동작 정보를 지정하여 서비스를 구성합니다. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][서비스 구성](../../../docs/framework/wcf/configuring-services.md)합니다.  
  
4.  서비스를 호스트합니다. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][호스팅 서비스](../../../docs/framework/wcf/hosting-services.md)합니다.  
  
5.  클라이언트 응용 프로그램을 빌드합니다. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][클라이언트 빌드](../../../docs/framework/wcf/building-clients.md)합니다.  
  
 이 단원의 항목은 이 순서를 따르지만 일부 시나리오에서는 첫 번째 단계부터 시작하지 않는 경우도 있습니다. 예를 들어 기존 서비스에 대한 클라이언트를 빌드하려면 5단계에서 시작합니다. 다른 사용자가 사용할 서비스를 빌드하는 경우 5단계를 건너뜁니다.  
  
 읽을 수도 있습니다 개발 하는 서비스 계약에 잘 알고 있다면 [확장성 소개](../../../docs/framework/wcf/introduction-to-extensibility.md)합니다. 서비스에 문제가 있는 경우 확인 [WCF 문제 해결 퀵 스타트](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md) 동일 하거나 유사한 문제가 있는 다른 지 여부를 확인 하려면.  
  
## <a name="see-also"></a>참고 항목  
 [서비스 계약 구현](../../../docs/framework/wcf/implementing-service-contracts.md)
