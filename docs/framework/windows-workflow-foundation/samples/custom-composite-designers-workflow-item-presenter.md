---
title: "사용자 지정 복합 디자이너 - 워크플로 항목 프리젠터 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f85224cf-9e30-44a5-9a81-3bc438a34364
caps.latest.revision: 16
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 16
---
# 사용자 지정 복합 디자이너 - 워크플로 항목 프리젠터
<xref:System.Activities.Presentation.WorkflowItemPresenter>는 임의의 활동을 배치할 수 있는 “끌어 놓기 영역”을 만들 수 있도록 하는 WF 디자이너 프로그래밍 모델의 키 형식입니다.이 샘플에서는 "끌어 놓기 영역" 같은 화면을 표시하는 활동 디자이너를 빌드하는 방법을 보여 줍니다.  
  
 이 샘플에서는 다음 작업을 수행하는 방법을 보여 줍니다.  
  
## 세부 항목  
  
-   <xref:System.Activities.Presentation.WorkflowItemPresenter>를 사용하여 사용자 지정 활동 디자이너 만들기  
  
-   메타데이터 저장소를 사용하여 사용자 지정 디자이너 등록  
  
-   다시 호스팅된 도구 상자를 선언적으로 또는 명령적으로 프로그래밍  
  
## 샘플 세부 정보  
 이 샘플의 코드는 다음을 보여 줍니다.  
  
-   `SimpleNativeActivity` 클래스에 대해 사용자 지정 활동 디자이너가 빌드됩니다.  
  
-   <xref:System.Activities.Presentation.WorkflowItemPresenter>를 사용하여 사용자 지정 활동 디자이너를 만드는 방법  
  
```xaml  
<sap:ActivityDesigner x:Class="Microsoft.Samples.UsingWorkflowItemPresenter.SimpleNativeDesigner"  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
    xmlns:sap="clr-namespace:System.Activities.Presentation;assembly=System.Activities.Presentation"  
    xmlns:sapv="clr-namespace:System.Activities.Presentation.View;assembly=System.Activities.Presentation">  
    <sap:ActivityDesigner.Resources>  
        <DataTemplate x:Key="Collapsed">  
            <StackPanel>  
                <TextBlock>This is the collapsed view</TextBlock>  
            </StackPanel>  
        </DataTemplate>  
        <DataTemplate x:Key="Expanded">  
            <StackPanel>  
                <TextBlock>Custom Text</TextBlock>  
                <sap:WorkflowItemPresenter Item="{Binding Path=ModelItem.Body, Mode=TwoWay}"  
                                        HintText="Please drop an activity here" />  
            </StackPanel>  
        </DataTemplate>  
        <Style x:Key="ExpandOrCollapsedStyle" TargetType="{x:Type ContentPresenter}">  
            <Setter Property="ContentTemplate" Value="{DynamicResource Collapsed}"/>  
            <Style.Triggers>  
                <DataTrigger Binding="{Binding Path=ShowExpanded}" Value="true">  
                    <Setter Property="ContentTemplate" Value="{DynamicResource Expanded}"/>  
                </DataTrigger>  
            </Style.Triggers>  
        </Style>  
    </sap:ActivityDesigner.Resources>  
    <Grid>  
        <ContentPresenter Style="{DynamicResource ExpandOrCollapsedStyle}" Content="{Binding}" />  
    </Grid>  
</sap:ActivityDesigner>  
```  
  
 WPF 데이터 바인딩을 사용하여 `ModelItem.Body`에 바인딩합니다.`ModelItem`은 디자이너가 사용될 기본 개체\(이 경우 **SimpleNativeActivity**\)를 참조하는 <xref:System.Activities.Presentation.WorkflowElementDesigner>의 속성입니다.  
  
#### 샘플을 설치, 빌드 및 실행하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 솔루션을 엽니다.  
  
2.  F5 키를 눌러 응용 프로그램을 컴파일하고 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\WorkflowItemPresenter`  
  
## 참고 항목  
 <xref:System.Activities.Presentation.WorkflowItemPresenter>   
 [Workflow Designer로 응용 프로그램 개발](../Topic/Developing%20Applications%20with%20the%20Workflow%20Designer.md)