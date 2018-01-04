---
title: ".NET Remoting 응용 프로그램을 WCF로 마이그레이션"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ',NET remoting [WCF]'
ms.assetid: 24793465-65ae-4308-8c12-dce4fd12a583
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b7d305adf1810832016cdafbb60fc025f17e0786
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="migrating-net-remoting-applications-to-wcf"></a>.NET Remoting 응용 프로그램을 WCF로 마이그레이션
**이 항목은 이전 버전의 기존 응용 프로그램과의 호환성을 위해 유지되며 새로운 개발에 권장되지 않는 레거시 기술과 관련된 것입니다. 분산 응용 프로그램은 이제 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]을 사용하여 개발해야 합니다.**  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 기존 .NET 원격 응용 프로그램과 함께 활용하는 두 가지 방법은 통합과 마이그레이션입니다. 통합 기능은 기존 .Net Remoting 2.0 코드를 수정하지 않고도 동시에 두 가지 기술에 대해 동일한 비즈니스 개체를 노출하도록 하여 사용자가 .Net Remoting 2.0과 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 함께 실행하도록 해줍니다. [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 2.0 이상에서 실행해야 통합을 수행할 수 있습니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 기능을 활용하려고 하지만 Remoting 2.0 시스템과의 유선 호환성은 필요하지 않을 경우, 전체 서비스를 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]로 마이그레이션할 수 있습니다. .NET Remoting 2.0으로부터 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]로 마이그레이션하려면 원격 개체의 인터페이스 및 해당 구성 설정으로 변경해야 합니다. 이 항목에 설명 되어 [에서 원격 Windows Communication Foundation을](http://go.microsoft.com/fwlink/?LinkId=74403)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [개념적 개요](../../../../docs/framework/wcf/conceptual-overview.md)
