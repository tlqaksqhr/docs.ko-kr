---
title: "오류 보내기 및 처리"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 98e8e04d-2ac9-4a33-ae08-462f757a7a14
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 57d522918d280c9a8a68fcd420b7216cc48216d7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="sending-and-handling-faults"></a>오류 보내기 및 처리
이 샘플에서는 <xref:System.ServiceModel.Activities.SendReply> 및 <xref:System.ServiceModel.Activities.ReceiveReply> 메시징 활동을 사용하여 예상된 오류와 예기치 않은 오류를 주고받는 방법을 보여 줍니다. 이 시나리오에서는 맨 처음 클라이언트 요청의 결과로 <xref:System.ServiceModel.Activities.Send.KnownTypes%2A> 컬렉션에 포함되어 있는 예상된 오류가 발생합니다. 그 이후 몇 번의 클라이언트 요청의 결과로 예기치 않은 오류가 발생한 다음 마지막 요청이 성공합니다.  
  
## <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  열기 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 마우스 오른쪽 단추로 클릭 하 여 승격 된 권한으로는 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 아이콘을 선택 하면 **관리자 권한으로 실행**합니다.  
  
2.  Faults.sln 솔루션 파일을 엽니다.  
  
3.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
4.  서비스 프로젝트를 실행합니다.  
  
    1.  **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭는 `FaultService` 프로젝트를 마우스 선택 **시작 프로젝트로 설정**합니다.  
  
    2.  Ctrl+F5를 누릅니다.  
  
5.  다른 복사본을 열고 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 마우스 오른쪽 단추로 클릭 하 여 승격 된 권한으로는 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 아이콘을 선택 하면 **관리자 권한으로 실행**합니다.  
  
6.  Faults.sln 솔루션 파일을 엽니다.  
  
7.  클라이언트 프로젝트를 실행합니다.  
  
    1.  **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭는 `FaultClient` 프로젝트를 마우스 선택 **시작 프로젝트로 설정**합니다.  
  
    2.  Ctrl+F5를 누릅니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\Faults`  
  
## <a name="see-also"></a>참고 항목
