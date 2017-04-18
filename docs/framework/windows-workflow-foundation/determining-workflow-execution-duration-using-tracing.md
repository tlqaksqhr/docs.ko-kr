---
title: "추적을 사용하여 워크플로 실행 기간 확인 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f04ad0fd-edc7-4cbc-8979-356f2a1131c4
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# 추적을 사용하여 워크플로 실행 기간 확인
이 항목에서는 성공적으로 완료된 자체 호스팅되는 워크플로가 실행하는 데 걸리는 시간을 워크플로 추적을 사용하여 확인하는 방법을 보여 줍니다.  
  
### 워크플로 추적을 사용하여 워크플로 응용 프로그램 실행 기간을 확인하려면  
  
1.  [!INCLUDE[vs2010](../../../includes/vs2010-md.md)]을 엽니다.**파일**, **새로 만들기**, **프로젝트**를 차례로 선택합니다.**C\#**에서 **Workflow** 노드를 선택합니다.템플릿 목록에서 **워크플로 콘솔 응용 프로그램**을 선택합니다.새 프로젝트의 이름을 `WorkflowDurationTracing`으로 지정하고 **확인**을 클릭합니다.  
  
2.  Workflow1.xaml을 엽니다.<xref:System.Activities.Statements.Delay> 활동을 디자이너 화면으로 끌어서 놓습니다.활동의 Duration 속성에 00:00:10 값\(10초\)을 할당합니다.  
  
3.  **시작**, **실행**을 차례로 클릭하고 `eventvwr.exe`를 입력하여 이벤트 뷰어를 엽니다.  
  
4.  워크플로 추적을 사용하도록 설정하지 않은 경우 **응용 프로그램 및 서비스 로그**, **Microsoft**, **Windows**, **응용 프로그램 서버\-응용 프로그램**을 차례로 확장합니다.**보기**, **분석 및 디버그 로그 표시**를 선택합니다.**디버그**를 마우스 오른쪽 단추로 클릭하고 **로그 사용**을 선택합니다.워크플로가 실행된 후 추적 내용을 볼 수 있도록 이벤트 뷰어를 열어 둡니다.  
  
5.  Ctrl\+Shift\+B를 눌러 워크플로 응용 프로그램을 실행합니다.  
  
6.  이벤트 뷰어에서 ID가 1009인 최근 이벤트 및 다음과 비슷한 메시지를 찾습니다.메시지가 기록된 시간을 기록해 둡니다.  
  
 **Parent Activity '', DisplayName: '', InstanceId: '' scheduled child Activity 'WorkflowDurationTracking.Workflow1', DisplayName: 'Workflow1', InstanceId: '1'.**  
  
7.  ID가 1001인 다른 최근 이벤트 및 다음과 비슷한 메시지를 찾습니다.이 메시지의 기록된 값에서 이전 메시지 시간을 빼서 워크플로 실행 기간을 확인합니다. 이 시간은 10초 정도여야 합니다.  
  
 **WorkflowInstance ID: '1bbac57b\-3322\-498e\-9e27\-8833fda3a5bf'가 Closed 상태에서 완료되었습니다.**  
  
## 참고 항목  
 [워크플로 추적](../../../docs/framework/windows-workflow-foundation//workflow-tracing.md)   
 [Windows Server App Fabric 모니터링](http://go.microsoft.com/fwlink/?LinkId=201273)   
 [App Fabric을 사용한 응용 프로그램 모니터링](http://go.microsoft.com/fwlink/?LinkId=201275)