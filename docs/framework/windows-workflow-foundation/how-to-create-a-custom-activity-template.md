---
title: "방법: 사용자 지정 활동 템플릿 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6760a5cc-6eb8-465f-b4fa-f89b39539429
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# 방법: 사용자 지정 활동 템플릿 만들기
사용자 지정 활동 템플릿은 사용자가 각 활동을 개별적으로 만들지 않고 속성 및 기타 설정을 수동으로 구성하지 않아도 되도록 사용자 지정 복합 활동을 비롯한 여러 활동의 구성을 사용자 지정하는 데 사용됩니다.이러한 사용자 지정 템플릿은 [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] 의 **도구 상자**에서 사용하거나, 사용자가 미리 구성된 디자인 화면에 끌어 놓을 수 있는 재호스팅된 디자이너에서 사용할 수 있습니다.[!INCLUDE[wfd2](../../../includes/wfd2-md.md)]는 이러한 템플릿의 좋은 예제인 [메시징 활동 디자이너](../Topic/Messaging%20Activity%20Designers.md) 범주의 [SendAndReceiveReply 템플릿 디자이너](../Topic/SendAndReceiveReply%20Template%20Designer.md) 및 [ReceiveAndSendReply 템플릿 디자이너](../Topic/ReceiveAndSendReply%20Template%20Designer.md)와 함께 제공됩니다.  
  
 이 항목의 첫 번째 절차에서는 **Delay** 활동에 대한 사용자 지정 활동 템플릿을 만드는 방법을 설명하고 두 번째 절차에서는 [!INCLUDE[wfd2](../../../includes/wfd2-md.md)]에서 사용자 지정 템플릿을 사용할 수 있도록 하여 해당 템플릿이 제대로 작동하는지 확인하는 방법을 간략하게 설명합니다.  
  
 사용자 지정 활동 템플릿은 <xref:System.Activities.Presentation.IActivityTemplateFactory>를 구현해야 합니다.인터페이스에는 템플릿에 사용되는 활동 인스턴스를 만들고 구성할 수 있는 단일 <xref:System.Activities.Presentation.IActivityTemplateFactory.Create%2A> 메서드가 있습니다.  
  
### Delay 활동에 대한 템플릿을 만들려면  
  
1.  [!INCLUDE[vs2010](../../../includes/vs2010-md.md)]을 시작합니다.  
  
2.  **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 선택합니다.  
  
     **새 프로젝트** 대화 상자가 열립니다.  
  
3.  **프로젝트 형식** 창에서 원하는 언어에 따라 **Visual C\#** 프로젝트 또는 **Visual Basic** 그룹의 **워크플로**를 선택합니다.  
  
4.  **템플릿** 창에서 **활동 라이브러리**를 선택합니다.  
  
5.  **이름** 상자에 `DelayActivityTemplate`을 입력합니다.  
  
6.  **위치** 및 **솔루션 이름** 텍스트 상자의 기본값을 그대로 두고 **확인**을 클릭합니다.  
  
7.  **솔루션 탐색기**에서 DelayActivityTemplate 프로젝트의 References 디렉터리를 마우스 오른쪽 단추로 클릭하고 **참조 추가**를 선택하여 **참조 추가** 대화 상자를 엽니다.  
  
8.  **.NET** 탭으로 이동하고 왼쪽의 **구성 요소 이름** 열에서 **PresentationFramework**를 선택한 다음 **확인**을 클릭하여 PresentationFramework.dll 파일에 대한 참조를 추가합니다.  
  
9. 이 절차를 반복하여 System.Activities.Presentation.dll 및 WindowsBase.dll 파일에 대한 참조를 추가합니다.  
  
10. **솔루션 탐색기**에서 DelayActivityTemplate 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가**를 선택한 다음 **새 항목**을 선택하여 **새 항목 추가** 대화 상자를 엽니다.  
  
11. **클래스** 템플릿을 선택하고 이름을 MyDelayTemplate으로 지정한 다음 **확인**을 클릭합니다.  
  
12. MyDelayTemplate.cs 파일을 열고 다음 문을 추가합니다.  
  
    ```  
  
    //Namespaces added  
    using System.Activities;  
    using System.Activities.Statements;  
    using System.Activities.Presentation;  
    using System.Windows;  
  
    ```  
  
13. 다음 코드를 사용하여 `MyDelayActivity` 클래스를 통해 <xref:System.Activities.Presentation.IActivityTemplateFactory>를 구현합니다.그러면 지연 기간이 10초로 구성됩니다.  
  
    ```  
  
    public sealed class MyDelayActivity : IActivityTemplateFactory  
    {  
        public Activity Create(System.Windows.DependencyObject target)  
        {  
            return new System.Activities.Statements.Delay  
            {  
                DisplayName = "DelayActivityTemplate",  
                Duration = new TimeSpan(0, 0, 10)  
  
            };  
        }  
    }  
  
    ```  
  
14. **빌드** 메뉴에서 **솔루션 빌드**를 선택하여 DelayActivityTemplate.dll 파일을 생성합니다.  
  
### Workflow Designer에서 템플릿을 사용할 수 있도록 하려면  
  
1.  **솔루션 탐색기**에서 DelayActivityTemplate 솔루션을 마우스 오른쪽 단추로 클릭하고 **추가**를 선택한 다음 **새 프로젝트**를 선택하여 **새 프로젝트 추가** 대화 상자를 엽니다.  
  
2.  **워크플로 콘솔 응용 프로그램** 템플릿을 선택하고 이름을 `CustomActivityTemplateApp`로 지정한 다음 **확인**을 클릭합니다.  
  
3.  **솔루션 탐색기**에서 CustomActivityTemplateApp 프로젝트의 References 디렉터리를 마우스 오른쪽 단추로 클릭하고 **참조 추가**를 선택하여 **참조 추가** 대화 상자를 엽니다.  
  
4.  **프로젝트** 탭으로 이동하고 왼쪽의 **프로젝트 이름** 열에서 **DelayActivityTemplate**을 선택한 다음 **확인**을 클릭하여 첫 번째 절차에서 만든 DelayActivityTemplate.dll 파일에 대한 참조를 추가합니다.  
  
5.  **솔루션 탐색기**에서 CustomActivityTemplateApp 프로젝트를 마우스 오른쪽 단추로 클릭하고 **빌드**를 선택하여 응용 프로그램을 컴파일합니다.  
  
6.  **솔루션 탐색기**에서 CustomActivityTemplateApp 프로젝트를 마우스 오른쪽 단추로 클릭한 다음 **시작 프로젝트로 설정**을 선택합니다.  
  
7.  **디버그** 메뉴에서 **디버깅하지 않고 시작**을 선택한 다음 cmd.exe 창에서 메시지가 표시되면 아무 키나 눌러 계속합니다.  
  
8.  Workflow1.xaml 파일을 열고 **도구 상자**를 엽니다.  
  
9. **DelayActivityTemplate** 범주에서 **MyDelayActivity** 템플릿을 찾아디자인 화면으로 끌어 옵니다.**속성** 창에서 `Duration` 속성이 10초로 설정되었는지 확인합니다.  
  
## 예제  
 MyDelayActivity.cs 파일에 다음 코드가 들어 있어야 합니다.  
  
```  
  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
  
//Namespaces added  
using System.Activities;  
using System.Activities.Statements;  
using System.Activities.Presentation;  
using System.Windows;  
  
namespace DelayActivityTemplate  
{  
    public sealed class MyDelayActivity : IActivityTemplateFactory  
    {  
        public Activity Create(System.Windows.DependencyObject target)  
        {  
            return new System.Activities.Statements.Delay  
            {  
                DisplayName = "DelayActivityTemplate",  
                Duration = new TimeSpan(0, 0, 10)  
  
            };  
        }  
    }  
}  
  
```  
  
## 참고 항목  
 <xref:System.Activities.Presentation.IActivityTemplateFactory>   
 [워크플로 디자인 환경 사용자 지정](../../../docs/framework/windows-workflow-foundation//customizing-the-workflow-design-experience.md)