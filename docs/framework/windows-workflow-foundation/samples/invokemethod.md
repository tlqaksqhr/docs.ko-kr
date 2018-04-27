---
title: InvokeMethod
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 04988eb3-65f8-456d-b1bd-509f5d05a57c
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f988f206fbd84b7b7d47fb3bd540420601ba30c9
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="invokemethod"></a>InvokeMethod
이 샘플에서는 <xref:System.Activities.Statements.InvokeMethod> 활동을 사용하여 클래스의 메서드를 호출하는 여러 가지 방법을 보여 줍니다.  
  
 메서드는 클래스에 속하며 클래스에 포함된 작업 집합을 나타냅니다. <xref:System.Activities.Statements.InvokeMethod> 활동을 사용하면 개체 또는 형식에 대해 메서드를 호출하고, 매개 변수를 전달하고, 반환 값을 가져올 수 있습니다. 메서드는 동기적으로 또는 비동기적으로 호출할 수 있습니다.  
  
## <a name="sample-details"></a>샘플 세부 정보  
 이 샘플에서는 <xref:System.Activities.Statements.InvokeMethod> 활동을 사용하여 다음과 같은 작업을 수행합니다.  
  
1.  매개 변수를 사용하지 않고 인스턴스 메서드를 호출합니다.  
  
2.  두 개의 매개 변수(<xref:System.String> 및 <xref:System.Int32>)를 사용하여 인스턴스 메서드를 호출합니다.  
  
3.  두 개의 매개 변수(<xref:System.String> 및 <xref:System.Int32>)와 <xref:System.String>[] 형식의 매개 변수 배열을 사용하여 인스턴스 메서드를 호출합니다.  
  
4.  <xref:System.Int32> 형식의 두 매개 변수와 <xref:System.Int32> 형식의 결과를 사용하여 인스턴스 메서드를 호출합니다. 이 경우 결과 값은 변수에 바인딩되어 다른 활동에 사용됩니다. 이 결과 값은 <xref:System.Activities.Statements.WriteLine> 활동을 사용하여 콘솔에 표시됩니다.  
  
5.  <xref:System.String> 및 <xref:System.Int32> 형식의 두 매개 변수를 사용하여 정적 메서드를 호출합니다.  
  
6.  <xref:System.String> 형식의 제네릭 매개 변수 하나를 사용하여 인스턴스 메서드를 호출합니다.  
  
7.  <xref:System.String> 및 <xref:System.Int32> 형식의 두 제네릭 매개 변수를 사용하여 정적 메서드를 호출합니다.  
  
8.  <xref:System.String> 형식의 참조로 전달되는 매개 변수 하나가 있는 인스턴스 메서드를 호출합니다. 이 경우 참조 매개 변수는 변수 `outParam`에 바인딩되어 다른 활동에 사용됩니다. 이 결과 값은 <xref:System.Activities.Statements.WriteLine> 활동을 사용하여 콘솔에 표시됩니다.  
  
9. 비동기 인스턴스 메서드를 호출합니다.  
  
10. 두 개의 <xref:System.Activities.Statements.InvokeMethod> 활동을 사용하여 동일한 개체 인스턴스에 대해 두 개의 서로 다른 메서드를 호출합니다.  
  
11. 개체 인스턴스에 값을 저장합니다.  
  
12. 개체 인스턴스에서 값을 검색합니다.  
  
## <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
 이 샘플은 두 가지 버전으로 제공됩니다. 이 샘플의 첫 번째 버전의 사용법을 보여 줍니다. <xref:System.Activities.Statements.InvokeMethod> C# 코드를 통해 Windows WF (Workflow Foundation) 프로그래밍 모델을 사용 하 고 CodedWorkflow\CS 폴더에 있습니다. DesignerWorkflow\CS 폴더에 있는 두 번째 버전에서는 XAML을 통해 <xref:System.Activities.Statements.InvokeMethod>를 사용하는 방법을 보여 줍니다.  
  
#### <a name="to-run-the-coded-workflow-sample"></a>코딩된 워크플로 샘플을 실행하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 CodedWorkflow\CS 폴더에 있는 InvokeMethodUsage.sln 솔루션 파일을 엽니다.  
  
2.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
3.  Ctrl+F5를 눌러 솔루션을 실행합니다.  
  
#### <a name="to-run-the-designer-workflow-sample"></a>디자이너 워크플로 샘플을 실행하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 DesignerWorkflow\CS 폴더에 있는 InvokeMethodUsage.sln 솔루션 파일을 엽니다.  
  
2.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
3.  Ctrl+F5를 눌러 솔루션을 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InvokeMethod`