---
title: "ModelItem 편집 컨텍스트 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7f9f1ea5-0147-4079-8eca-be94f00d3aa1
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# ModelItem 편집 컨텍스트 사용
<xref:System.Activities.Presentation.Model.ModelItem> 편집 컨텍스트는 호스트 응용 프로그램이 디자이너와 통신할 때 사용하는 개체입니다.<xref:System.Activities.Presentation.EditingContext>는 사용할 수 있는 메서드 두 개\(<xref:System.Activities.Presentation.EditingContext.Items%2A> 및 <xref:System.Activities.Presentation.EditingContext.Services%2A>\)를 노출합니다.  
  
## Items 컬렉션  
 <xref:System.Activities.Presentation.EditingContext.Items%2A> 컬렉션은 호스트와 디자이너 간에 공유되는 데이터나 모든 디자이너에서 사용할 수 있는 데이터에 액세스할 때 사용됩니다.이 컬렉션에는 <xref:System.Activities.Presentation.ContextItemManager> 클래스를 통해 액세스되는 다음 기능이 있습니다.  
  
1.  <xref:System.Activities.Presentation.ContextItemManager.GetValue%2A>  
  
2.  <xref:System.Activities.Presentation.ContextItemManager.Subscribe%2A>  
  
3.  <xref:System.Activities.Presentation.ContextItemManager.Unsubscribe%2A>  
  
4.  <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A>  
  
## Services 컬렉션  
 <xref:System.Activities.Presentation.EditingContext.Services%2A> 컬렉션은 디자이너가 호스트와 상호 작용하는 데 사용하는 서비스나 모든 디자이너에서 사용하는 서비스에 액세스할 때 사용됩니다.이 컬렉션에는 다음과 같은 중요한 메서드가 있습니다.  
  
1.  <xref:System.Activities.Presentation.ServiceManager.Publish%2A>  
  
2.  <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A>  
  
3.  <xref:System.Activities.Presentation.ServiceManager.Unsubscribe%2A>  
  
4.  <xref:System.Activities.Presentation.ServiceManager.GetService%2A>  
  
## 작업에 디자이너 할당  
 작업에 사용되는 디자이너를 지정하려면 Designer 특성을 사용합니다.  
  
```  
[Designer(typeof(MyClassDesigner))]  
public sealed class MyClass : CodeActivity  
{  
  
```  
  
## 서비스 만들기  
 디자이너와 호스트 간에 정보 전달자 역할을 하는 서비스를 만들려면 인터페이스와 구현을 만들어야 합니다.인터페이스는 <xref:System.Activities.Presentation.ServiceManager.Publish%2A> 메서드에서 서비스의 멤버를 정의하는 데 사용되고 구현에는 서비스에 대한 논리가 포함됩니다.다음 코드 예제에서는 서비스 인터페이스와 구현이 생성됩니다.  
  
```  
public interface IMyService  
    {  
        IEnumerable<string> GetValues(string DisplayName);  
    }  
  
    public class MyServiceImpl : IMyService  
    {  
        public IEnumerable<string> GetValues(string DisplayName)  
        {  
            return new string[]  {   
                DisplayName + " One",   
                DisplayName + " Two",  
                "Three " + DisplayName  
            } ;  
        }  
    }  
  
```  
  
## 서비스 게시  
 디자이너에서 서비스를 사용하려면 먼저 <xref:System.Activities.Presentation.ServiceManager.Publish%2A> 메서드를 사용하여 호스트가 서비스를 게시해야 합니다.  
  
```  
this.Context.Services.Publish<IMyService>(new MyServiceImpl);  
```  
  
## 서비스 구독  
 디자이너는 <xref:System.Activities.Presentation.WorkflowViewElement.OnModelItemChanged%2A> 메서드에서 <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A> 메서드를 사용하여 서비스에 대한 액세스 권한을 얻습니다.다음 코드 조각에서는 서비스를 구독하는 방법을 보여 줍니다.  
  
```  
protected override void OnModelItemChanged(object newItem)  
{  
    if (!subscribed)  
    {  
        this.Context.Services.Subscribe<IMyService>(  
            servInstance =>  
            {  
                listBox1.ItemsSource = servInstance.GetValues(this.ModelItem.Properties["DisplayName"].ComputedValue.ToString());  
            }  
            );  
        subscribed = true;   
    }  
}  
  
```  
  
## Items 컬렉션을 사용하여 데이터 공유  
 Items 컬렉션 사용은 Publish 대신 <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A>가 사용된다는 점을 제외하고 Services 컬렉션 사용과 유사합니다.이 컬렉션은 복잡한 기능보다 디자이너와 호스트 간에 간단한 데이터를 공유하는 데 보다 적합합니다.  
  
## EditingContext 호스트 항목 및 서비스  
 .NET Framework는 편집 컨텍스트를 통해 액세스되는 많은 기본 제공 항목과 서비스를 제공합니다.  
  
 항목:  
  
-   <xref:System.Activities.Presentation.Hosting.AssemblyContextControlItem>: 식 편집기와 같은 컨트롤의 워크플로 내에서 사용될 참조된 로컬 어셈블리 목록을 관리합니다.  
  
-   <xref:System.Activities.Presentation.Hosting.ReadOnlyState>: 디자이너가 읽기 전용 상태인지 여부를 나타냅니다.  
  
-   <xref:System.Activities.Presentation.View.Selection>: 현재 선택된 개체의 컬렉션을 정의합니다.  
  
-   <xref:System.Activities.Presentation.Hosting.WorkflowCommandExtensionItem>:  
  
-   <xref:System.Activities.Presentation.WorkflowFileItem>: 현재 편집 세션의 기반이 되는 파일에 대한 정보를 제공합니다.  
  
 서비스:  
  
-   <xref:System.Activities.Presentation.Model.AttachedPropertiesService>: <xref:System.Activities.Presentation.Model.AttachedPropertiesService.AddProperty%2A>를 사용하여 현재 인스턴스에 속성을 추가할 수 있도록 합니다.  
  
-   <xref:System.Activities.Presentation.View.DesignerView>: 디자이너 캔버스의 속성에 액세스할 수 있도록 합니다.  
  
-   <xref:System.Activities.Presentation.IActivityToolboxService>: 도구 상자의 콘텐츠를 업데이트할 수 있도록 합니다.  
  
-   <xref:System.Activities.Presentation.Hosting.ICommandService>: 사용자 지정 제공 서비스 구현과 디자이너 명령\(예: 상황에 맞는 메뉴\)을 통합하는 데 사용됩니다.  
  
-   <xref:System.Activities.Presentation.Debug.IDesignerDebugView>: 디자이너 디버거에 기능을 제공합니다.  
  
-   <xref:System.Activities.Presentation.View.IExpressionEditorService>: 식 편집기 대화 상자에 액세스할 수 있도록 합니다.  
  
-   <xref:System.Activities.Presentation.IIntegratedHelpService>: 디자이너에 통합된 도움말 기능을 제공합니다.  
  
-   <xref:System.Activities.Presentation.Validation.IValidationErrorService>: <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A>를 사용하여 유효성 검사 오류에 액세스할 수 있도록 합니다.  
  
-   <xref:System.Activities.Presentation.IWorkflowDesignerStorageService>: 데이터를 저장하고 검색하는 내부 서비스를 제공합니다.이 서비스는 .Net Framework에서 내부적으로 사용되며 외부에서 사용하기 위한 것이 아닙니다.  
  
-   <xref:System.Activities.Presentation.IXamlLoadErrorService>: <xref:System.Activities.Presentation.IXamlLoadErrorService.ShowXamlLoadErrors%2A>를 사용하여 XAML 로드 오류 컬렉션에 액세스할 수 있도록 합니다.  
  
-   <xref:System.Activities.Presentation.Services.ModelService>: 디자이너에서 편집 중인 워크플로 모델과 상호 작용하는 데 사용됩니다.  
  
-   <xref:System.Activities.Presentation.Model.ModelTreeManager>: <xref:System.Activities.Presentation.Model.ModelItem.Root%2A>를 사용하여 모델 항목 트리의 루트에 액세스할 수 있도록 합니다.  
  
-   <xref:System.Activities.Presentation.UndoEngine>: 실행 취소 및 다시 실행 기능을 제공합니다.  
  
-   <xref:System.Activities.Presentation.Services.ViewService>: 시각적 요소를 기본 모델 항목에 매핑합니다.  
  
-   <xref:System.Activities.Presentation.View.ViewStateService>: 모델 항목의 뷰 상태를 저장합니다.  
  
-   <xref:System.Activities.Presentation.View.VirtualizedContainerService>: 가상 컨테이너 UI 동작을 사용자 지정하는 데 사용됩니다.  
  
-   <xref:System.Activities.Presentation.Hosting.WindowHelperService>: 이벤트 알림의 대리자를 등록 및 등록 취소하는 데 사용됩니다.창 소유자를 설정할 수도 있습니다.