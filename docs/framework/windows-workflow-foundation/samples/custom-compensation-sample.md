---
title: "사용자 지정 보정 샘플"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 385920da-9284-44bf-9fe9-0d87c7478ec5
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c3a9745c0cdd3a2d7050aed083d2eee5dfd4aaaf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="custom-compensation-sample"></a>사용자 지정 보정 샘플
이 샘플에서는 <xref:System.Activities.Statements.CompensableActivity>와 해당 보정 처리기를 사용하여 사용자 지정 보정 논리를 정의하는 방법을 보여 줍니다. 이 샘플에서 모델링하는 시나리오는 트럭 렌탈 대행사입니다.  
  
## <a name="sample-details"></a>샘플 세부 정보  
 시뮬레이션하는 단계는 다음과 같습니다.  
  
1.  사용자가 지정된 날짜에 대한 트럭 렌탈 가격 견적을 요청합니다.  
  
2.  세 개의 트럭 회사에 연락하여 세 개의 견적 가격을 받습니다.  
  
3.  사용자는 하나의 트럭 견적 가격을 선택하고 신용 카드로 주문합니다.  
  
4.  응용 프로그램은 나머지 두 개의 트럭 가격 견적을 취소합니다.  
  
5.  응용 프로그램은 예약 날짜 10일 전까지 취소할 경우 프리미엄 계좌가 아닌 일반 계좌의 경우 환불되지 않는 서비스 요금을 청구합니다.  
  
6.  응용 프로그램은 트럭 렌탈 요금을 청구합니다.  
  
7.  응용 프로그램은 예약 날짜와 고객이 예약을 취소하기로 결정한 날짜 중 빠른 날짜까지 기다립니다.  
  
8.  고객이 예약을 취소하는 경우 <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> 사용자 지정 보정 논리는 다음 논리에 따라 실행됩니다.  
  
    1.  고객의 계좌가 프리미엄 계좌가 아니고 현재 시점부터 예약 날짜까지 남은 날짜가 10일 미만인 경우 서비스 요금이 청구되며, 이외의 경우에는 응용 프로그램이 서비스 요금을 환불합니다.  
  
    2.  나머지 보정 가능한 활동(트럭 주문 + 트럭 주문 요금)은 실행 순서의 반대로 보정하는 기본 보정 논리에 따라 실행됩니다.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 사용하여 CustomCompensation.sln 솔루션을 엽니다. 솔루션은 \WF\Basic\Compensation\CustomCompensation 디렉터리에 있습니다.  
  
2.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
3.  Ctrl+F5를 눌러 응용 프로그램을 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Compensation\CustomCompensation`  
  
## <a name="see-also"></a>참고 항목
