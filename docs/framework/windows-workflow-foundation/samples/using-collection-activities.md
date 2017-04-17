---
title: "컬렉션 활동 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e1977cf8-1695-4071-b946-7046fe39601e
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# 컬렉션 활동 사용
이 샘플에서는 <xref:System.Collections.ICollection> 인터페이스를 구현하는 클래스를 사용하여 <xref:System.Activities.Statements.AddToCollection%601>, <xref:System.Activities.Statements.ClearCollection%601>, <xref:System.Activities.Statements.ExistsInCollection%601> 및 <xref:System.Activities.Statements.RemoveFromCollection%601> 컬렉션 활동을 사용하는 방법과 컬렉션을 반복하여 컬렉션의 각 요소 내용을 출력하는 사용자 지정 활동을 만드는 방법을 보여 줍니다.`PrintCollection`이라는 사용자 지정 활동은 `Numbers`라는 컬렉션의 항목 멤버를 콘솔에 출력합니다.  
  
 다음 표에서는 워크플로에 대한 컬렉션 조작 기능을 제공하는 네 가지 활동을 설명합니다.  
  
|활동 이름|설명|  
|-----------|--------|  
|<xref:System.Activities.Statements.AddToCollection%601>|컬렉션에 항목을 추가합니다.|  
|<xref:System.Activities.Statements.ClearCollection%601>|컬렉션에서 모든 항목을 지웁니다.|  
|<xref:System.Activities.Statements.ExistsInCollection%601>|지정된 항목이 컬렉션에 있는 경우 `true`를 반환합니다.|  
|<xref:System.Activities.Statements.RemoveFromCollection%601>|컬렉션에서 항목을 제거합니다.|  
  
 이 샘플은 두 개의 솔루션으로 구성되어 있습니다. 그 중 하나는 CodedWorkflow 디렉터리에 있고, 다른 하나는 DesignerWorkflow 디렉터리에 있습니다.이들 솔루션은 동일한 용도로 활동을 사용하는 서로 다른 두 가지 방법을 보여 줍니다.  
  
||||  
|-|-|-|  
|솔루션|설명|기본 파일|  
|CodedWorkflow|컬렉션 활동을 프로그래밍 방식으로 호출하는 방법을 보여 주는 샘플 클라이언트 응용 프로그램입니다.|**PrintCollection.cs**: 컬렉션의 모든 항목을 콘솔에 출력하는 도우미 활동입니다.<br /><br /> **Program.cs**: 일련의 컬렉션 활동이 포함되어 있는 시퀀스 활동을 프로그래밍 방식으로 빌드하고 이를 실행합니다.|  
|DesignerWorkflow|컬렉션 활동을 워크플로 디자이너에서 선언적으로 사용하는 방법을 보여 주는 샘플 클라이언트 응용 프로그램입니다.|**CollectionWorkflow.xaml**: 컬렉션 활동을 사용하는 디자이너를 통해 선언적으로 만든 워크플로입니다.<br /><br /> **PrintCollection.cs**: 컬렉션의 모든 항목을 콘솔에 출력하는 도우미 활동입니다.<br /><br /> **Program.cs**: CollectionWorkflow.xaml에서 설명하는 워크플로를 호출합니다.|  
  
 이 데모에서는 `PrintCollection`이라는 사용자 정의된 활동을 통해 `Numbers` 컬렉션의 항목 멤버가 콘솔에 출력됩니다.  
  
#### 이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 Collection.sln 솔루션 파일을 엽니다.  
  
2.  Ctrl\+Shift\+B를 눌러 솔루션을 빌드합니다.  
  
3.  Ctrl\+F5를 눌러 솔루션을 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Collection`  
  
## 참고 항목