---
title: "NoPersistScope 활동 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9a0baeb7-a05c-4fac-b905-252758cb71bb
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# NoPersistScope 활동
이 샘플에서는 워크플로 내의 serialize할 수 없고 삭제 가능한 상태를 처리하는 방법을 보여 줍니다.이때 워크플로에서 serialize 불가능 상태를 지속하려고 시도하지 않는다는 점이 중요하며 삭제 가능한 개체를 워크플로에 사용하고 나면 이를 정리해야 한다는 점도 중요합니다.  
  
## 세부 항목  
 `NoPersistScope` 사용자 지정 활동 및 디자이너  
  
## NoPersistZone 활동 사용  
 샘플 워크플로를 실행하면 `CreateTextWriter`라는 사용자 지정 활동을 통해<xref:System.IO.TextWriter> 형식의 개체를 만들고 이 개체를 워크플로 변수에 저장합니다.<xref:System.IO.TextWriter>이 <xref:System.IDisposable> 개체인 경우.샘플이 실행되는 디렉터리의 'out.txt'라는 파일에 텍스트를 쓰도록 구성되어 있는 이 <xref:System.IO.TextWriter>는 <xref:System.Activities.Statements.WriteLine> 활동에 사용되며 사용자가 콘솔에 입력하는 모든 텍스트를 그대로 반복합니다.  
  
 이 echo 논리는 워크플로가 지속되지 않도록 하는 `NoPersistScope` 활동 내에서 실행됩니다. 이 활동의 코드도 이 샘플에 포함되어 있습니다.사용자가 콘솔에 `unload`를 입력하면 호스트에서 워크플로 인스턴스를 지속하려고 시도하지만 워크플로가 `NoPersistScope`를 벗어나지 못하므로 이 작업이 제한 시간을 초과하게 됩니다.또한 이 워크플로에서는 <xref:System.IO.TextWriter> 개체 사용을 마쳤을 때 `Dispose`라는 사용자 지정 활동을 사용하여 이 개체를 삭제합니다.`Dispose` 활동은 Try 블록을 실행하는 동안 예외가 발생하더라도 문제 없이 실행되도록 하기 위해 <xref:System.IO.TextWriter> 변수가 선언된 <xref:System.Activities.Statements.TryCatch> 활동의 <xref:System.Activities.Statements.TryCatch.Finally%2A> 블록 내에 배치됩니다.  
  
 `exit`을 입력하면 워크플로 인스턴스를 완료하고 프로그램을 종료할 수 있습니다.  
  
#### 샘플을 실행하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 NoPersistZone.sln 솔루션을 엽니다.  
  
2.  솔루션을 빌드하려면 Ctrl\+Shift\+B를 누르거나 **빌드** 메뉴에서 **솔루션 빌드**를 선택합니다.  
  
3.  빌드가 성공적으로 완료되면 F5 키를 누르거나 **디버그** 메뉴에서 **디버깅 시작**을 선택합니다. 또는 Ctrl\+F5를 누르거나 **디버그** 메뉴에서 **디버깅하지 않고 시작**을 선택하여 디버깅 과정을 생략하고 시작할 수도 있습니다.  
  
#### 정리하려면\(옵션\)  
  
1.  SQL 인스턴스 저장소를 제거하려면 Cleanup.cmd를 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\NoPersistScope`  
  
## 참고 항목