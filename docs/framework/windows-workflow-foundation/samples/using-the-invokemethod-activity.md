---
title: "InvokeMethod 활동 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b6643550-d043-4ac7-8069-9c55ebbb4233
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# InvokeMethod 활동 사용
이 샘플에서는 <xref:System.Activities.Statements.InvokeMethod%601> 활동을 사용하여 public 클래스의 public 메서드를 호출하는 방법을 보여 줍니다.<xref:System.Activities.Statements.InvokeMethod%601> 활동을 사용하면 워크플로에서 개체에 대해 메서드를 호출하고, 매개 변수를 전달하고, 반환 값을 가져오고, 제네릭 메서드의 형식을 지정하고, 멤버를 동기화할지 비동기화할지 지정할 수 있습니다.  
  
 반환 값이 <xref:System.Activities.Statements.InvokeMethod.Result%2A> 속성으로 설정되는 비제네릭 버전의 <xref:System.Activities.Statements.InvokeMethod> 활동과 반환 값이 `TResult` 형식의 <xref:System.Activities.Statements.InvokeMethod.Result%601.Result%2A> 속성을 통해 반환되는 제네릭 버전의 <xref:System.Activities.Statements.InvokeMethod%601> 활동이 있습니다.  
  
 이 샘플에서는 다양한 메서드 형식을 호출하는 방법을 보여 줍니다.다음 목록에는 이 샘플에서 보여 주는 메서드 형식이 자세히 나와 있습니다.  
  
-   매개 변수를 사용하지 않고 인스턴스 메서드를 호출합니다.  
  
-   두 개의 매개 변수\(System.String 및 System.Int32\)를 사용하여 인스턴스 메서드를 호출합니다.  
  
-   두 개의 매개 변수\(System.String 및 System.Int32\)와 System.String\[\] 형식의 매개 변수 배열을 사용하여 인스턴스 메서드를 호출합니다.  
  
-   두 개의 매개 변수\(두 개의 System.Int32 숫자\)와 System.Int32 형식의 결과를 사용하여 인스턴스 메서드를 호출합니다.  
  
     반환 값은 변수에 바인딩되고 <xref:System.Activities.Statements.WriteLine> 활동을 사용하여 콘솔에 출력됩니다.  
  
-   두 개의 매개 변수\(System.String 및 System.Int32\)를 사용하여 정적 메서드를 호출합니다.  
  
-   제네릭 매개 변수 한 개\(System.String\)를 사용하여 인스턴스 메서드를 호출합니다.  
  
-   두 개의 제네릭 매개 변수\(System.String 및 System.Int32\)를 사용하여 정적 메서드를 호출합니다.  
  
-   참조\(System.String\)로 전달되는 매개 변수 한 개가 있는 인스턴스 메서드를 호출합니다.  
  
     참조된 매개 변수는 변수에 바인딩되고 <xref:System.Activities.Statements.WriteLine> 활동을 사용하여 콘솔에 출력됩니다.  
  
-   비동기 인스턴스 메서드를 호출합니다.  
  
## 이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 InvokeMethodUsage.sln 솔루션 파일을 엽니다.  
  
2.  Ctrl\+Shift\+B를 눌러 솔루션을 빌드합니다.  
  
3.  Ctrl\+F5를 눌러 솔루션을 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InvokeMethod`  
  
## 참고 항목