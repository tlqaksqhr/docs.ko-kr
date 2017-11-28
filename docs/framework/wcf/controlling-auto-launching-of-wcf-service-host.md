---
title: "WCF 서비스 호스트 자동 시작 제어"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: WcfOptions
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: dc89ed3ae41471af49fc92f31834f0ae268309dd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="controlling-auto-launching-of-wcf-service-host"></a>WCF 서비스 호스트 자동 시작 제어
여러 프로젝트가 포함된 같은 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 솔루션의 다른 프로젝트를 디버깅할 때 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 라이브러리 프로젝트에 대한 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 서비스 호스트(WcfSvcHost.exe)의 자동 시작 기능을 제어할 수 있습니다.  
  
 이렇게 하려면 마우스 오른쪽 단추로 클릭는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 프로젝트에 **솔루션 탐색기**, 선택 **속성**를 클릭 하 고 **WCF 옵션** 탭 합니다. **WCF 서비스 호스트 시작 동일한 솔루션의 다른 프로젝트를 디버깅할 때** 확인란은 기본적으로 사용 됩니다. 같은 솔루션의 다른 프로젝트를 디버깅할 때 이 특정 프로젝트에 대해 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 호스트가 시작되지 않게 하려면 이 확인란의 선택을 취소할 수 있습니다.  
  
 이 동작은 F5 키를 사용한 디버깅이나 이 프로젝트의 서비스 참조 추가 기능에는 영향을 주지 않습니다.  
  
 이 옵션은 다음 프로젝트에 사용할 수 있습니다.  
  
-   [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 라이브러리 프로젝트  
  
-   순차 워크플로 서비스 라이브러리 프로젝트  
  
-   상태 시스템 워크플로 서비스 라이브러리 프로젝트  
  
-   배포 서비스 라이브러리 프로젝트  
  
## <a name="see-also"></a>참고 항목  
 [WCF 서비스 호스트(WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
