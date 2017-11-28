---
title: Programming Model Item Tree
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0229efde-19ac-4bdc-a187-c6227a7bd1a5
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 18de9d7f9cedc40a6c143a4dae5567c9acf2cf88
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="programming-model-item-tree"></a>Programming Model Item Tree
이 샘플에서는 <xref:System.Activities.Presentation.Model.ModelItem> 트리 뷰에서 선언적 데이터 바인딩을 사용하여 [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)]을 탐색하는 방법을 보여 줍니다.  
  
## <a name="sample-details"></a>샘플 세부 정보  
 <xref:System.Activities.Presentation.Model.ModelItem> 트리는 [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] 인프라에서 편집할 기본 인스턴스에 대한 데이터를 노출하는 데 사용되는 추상화입니다. 다음 그림에서는 [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)] 내의 다양한 인프라 계층을 보여 줍니다.  
  
 ![Workflow Designer 아키텍처](../../../../docs/framework/windows-workflow-foundation/samples/media/workflowdesignerarch.JPG "WorkflowDesignerArch")  
  
 <xref:System.Activities.Presentation.Model.ModelItem>은 내부 값에 대한 포인터와 <xref:System.Activities.Presentation.Model.ModelProperty> 개체의 컬렉션으로 구성됩니다. <xref:System.Activities.Presentation.Model.ModelProperty> 개체는 속성의 이름 및 형식 같은 데이터와 값에 대한 포인터로 구성되며 이 값은 또 다른 <xref:System.Activities.Presentation.Model.ModelItem>입니다. 값 변환기는 <xref:System.Activities.Presentation.Model.ModelItem>에서 반환된 <xref:System.Activities.Presentation.Model.ModelProperty>의 일부를 조작하여 트리 뷰에 올바르게 나타나도록 하는 데 사용됩니다. 그런 다음 샘플에서는 다음 예제에 표시된 것과 같은 명령적 구문을 사용하여 <xref:System.Activities.Presentation.Model.ModelItem> 트리에 대해 명령적으로 프로그래밍하는 방법을 보여 줍니다.  
  
```csharp  
ModelItem mi = wd.Context.Services.GetService<ModelService>().Root;  
ModelProperty mp = mi.Properties["Activities"];  
mp.Collection.Add(new Persist());  
ModelItem justAdded = mp.Collection.Last();  
justAdded.Properties["DisplayName"].SetValue("new name");  
```  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 ProgrammingModelItemTree.sln 솔루션을 엽니다.  
  
2.  선택 하 여 솔루션을 빌드합니다 **솔루션 빌드** 에서 **빌드** 메뉴.  
  
3.  F5 키를 눌러 응용 프로그램을 실행합니다. 그러면 [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] 폼이 표시됩니다.  
  
4.  클릭는 **WF 로드** 로드 하는 단추는 <xref:System.Activities.Presentation.Model.ModelItem> 트리 뷰에 바인딩합니다.  
  
5.  클릭 하 고 **트리 변경** 단추를 트리에 항목이 추가 되 고 속성을 설정 하려면 앞의 코드가 실행 합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\ProgrammingModelItemTree`  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Data.IValueConverter>
