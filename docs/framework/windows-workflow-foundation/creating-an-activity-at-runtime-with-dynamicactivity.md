---
title: "동적 활동을 사용하여 런타임에 활동 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1af85cc6-912d-449e-90c5-c5db3eca5ace
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ebbd6e77c2c47754054a81f4b07d3d845cdcac00
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="creating-an-activity-at-runtime-with-dynamicactivity"></a>동적 활동을 사용하여 런타임에 활동 만들기
<xref:System.Activities.DynamicActivity>는 public 생성자를 사용하는 구체적이고 봉인된 클래스입니다. <xref:System.Activities.DynamicActivity>는 활동 DOM을 통해 런타임에 활동 기능을 어셈블하는 데 사용할 수 있습니다.  
  
## <a name="dynamicactivity-features"></a>DynamicActivity 기능  
 <xref:System.Activities.DynamicActivity>는 실행 속성, 인수 및 변수에 대한 액세스 권한이 있지만 자식 활동 예약, 추적 등과 같은 런타임 서비스에 대한 액세스 권한이 없습니다.  
  
 워크플로 <xref:System.Activities.Argument> 개체를 사용하여 최상위 속성을 설정할 수 있습니다. 명령적 코드에서는 새로운 형식의 CLR 속성을 사용하여 이러한 인수를 만듭니다. XAML에서는 `x:Class` 및 `x:Member` 태그를 사용하여 이러한 인수를 선언합니다.  
  
 <xref:System.Activities.DynamicActivity>를 사용하여 구성된 활동은 <xref:System.ComponentModel.ICustomTypeDescriptor>를 사용하여 디자이너에 연결됩니다. 다음 절차에 설명된 것처럼 디자이너에서 만든 활동은 <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A>를 사용하여 동적으로 로드할 수 있습니다.  
  
#### <a name="to-create-an-activity-at-runtime-using-imperative-code"></a>명령적 코드를 사용하여 런타임에 활동을 만들려면  
  
1.  [!INCLUDE[vs2010](../../../includes/vs2010-md.md)]를 엽니다.  
  
2.  선택 **파일**, **새**, **프로젝트**합니다. 선택 **Workflow 4.0** 아래 **Visual C#** 에 **프로젝트 형식** 창과 선택은 **v2010** 노드. 선택 **순차 워크플로 콘솔 응용 프로그램** 에 **템플릿** 창. 새 프로젝트의 이름을 DynamicActivitySample로 지정합니다.  
  
3.  HelloActivity 프로젝트에서 Workflow1.xaml을 마우스 오른쪽 단추로 클릭 하 고 선택 **삭제**합니다.  
  
4.  Program.cs를 엽니다. 다음 지시문을 파일의 맨 위에 추가합니다.  
  
    ```  
    using System.Collections.Generic;  
    ```  
  
5.  `Main` 메서드의 내용을 다음 코드로 바꿉니다. 이 코드는 단일 <xref:System.Activities.Statements.Sequence> 활동을 포함하는 <xref:System.Activities.Statements.WriteLine> 활동을 만든 다음 새 동적 활동의 <xref:System.Activities.DynamicActivity.Implementation%2A> 속성에 할당합니다.  
  
    ```csharp  
    //Define the input argument for the activity  
    var textOut = new InArgument<string>();  
    //Create the activity, property, and implementation  
                Activity dynamicWorkflow = new DynamicActivity()  
                {  
                    Properties =   
                    {  
                        new DynamicActivityProperty  
                        {  
                            Name = "Text",  
                            Type = typeof(InArgument<String>),  
                            Value = textOut  
                        }  
                    },  
                    Implementation = () => new Sequence()  
                    {  
                        Activities =   
                        {  
                            new WriteLine()  
                            {  
                                Text = new InArgument<string>(env => textOut.Get(env))  
                            }  
                        }  
                    }  
                };  
    //Execute the activity with a parameter dictionary  
                WorkflowInvoker.Invoke(dynamicWorkflow, new Dictionary<string, object> { { "Text", "Hello World!" } });  
                Console.ReadLine();  
    ```  
  
6.  응용 프로그램을 실행합니다. 텍스트 "Hello World!"와 함께 콘솔 창 표시 됩니다.  
  
#### <a name="to-create-an-activity-at-runtime-using-xaml"></a>XAML을 사용하여 런타임에 활동을 만들려면  
  
1.  [!INCLUDE[vs2010](../../../includes/vs2010-md.md)]를 엽니다.  
  
2.  선택 **파일**, **새**, **프로젝트**합니다. 선택 **Workflow 4.0** 아래 **Visual C#** 에 **프로젝트 형식** 창과 선택은 **v2010** 노드. 선택 **워크플로 콘솔 응용 프로그램** 에 **템플릿** 창. 새 프로젝트의 이름을 DynamicActivitySample로 지정합니다.  
  
3.  HelloActivity 프로젝트에서 Workflow1.xaml을 엽니다. 클릭는 **인수** 디자이너의 맨 아래에 옵션입니다. `In` 형식의 `TextToWrite`라는 새 `String` 인수를 만듭니다.  
  
4.  끌어서는 **WriteLine** 활동을는 **기본 형식** 디자이너 화면으로 도구 상자의 섹션. 값을 할당 `TextToWrite` 에 **텍스트** 작업의 속성입니다.  
  
5.  Program.cs를 엽니다. 다음 지시문을 파일의 맨 위에 추가합니다.  
  
    ```  
    using System.Activities.XamlIntegration;  
    ```  
  
6.  `Main` 메서드의 내용을 다음 코드로 대체합니다.  
  
    ```  
    Activity act2 = ActivityXamlServices.Load(@"Workflow1.xaml");  
                    results = WorkflowInvoker.Invoke(act2, new Dictionary<string, object> { { "TextToWrite", "HelloWorld!" } });  
    Console.ReadLine();  
    ```  
  
7.  응용 프로그램을 실행합니다. 텍스트 "Hello World!"와 함께 콘솔 창 나타납니다.  
  
8.  Workflow1.xaml 파일을 마우스 오른쪽 단추로 클릭는 **솔루션 탐색기** 선택 **코드 보기**합니다. 활동 클래스가 `x:Class`를 사용하여 만들어지고 속성은 `x:Property`를 사용하여 만들어집니다.  
  
## <a name="see-also"></a>참고 항목  
 [명령형 코드를 사용하여 워크플로, 활동 및 식 작성](../../../docs/framework/windows-workflow-foundation/authoring-workflows-activities-and-expressions-using-imperative-code.md)  
 [DynamicActivity 만들기](../../../docs/framework/windows-workflow-foundation/samples/dynamicactivity-creation.md)
