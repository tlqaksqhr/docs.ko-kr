---
title: "도구 상자 서비스 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 742212d0-445e-41ed-9739-9ee848ce7f1b
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# 도구 상자 서비스
이 샘플에서는 워크플로 컨텍스트를 기반으로 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 도구 상자 활동을 업데이트하는 방법을 보여 줍니다.이 샘플에는 사용자 지정 활동이 선택되었는지 여부에 따라 도구 상자 내용을 변경하는 워크플로가 포함되어 있습니다.  
  
## 추가 설명  
 워크플로를 작성할 때 고객은 일반적으로 도구 상자가 상황에 맞게 표시되기를 원합니다. 예를 들어 사용자가 워크플로에 특정 활동을 추가하는 경우 도구 상자에 몇 가지 추가 활동이 표시되도록 할 수 있습니다.워크플로에서 활동을 제거하는 경우 도구 상자는 도메인 요구 사항을 기반으로 적절하게 응답해야 합니다.  
  
 다시 호스팅된 Workflow Designer에서 도구 상자 컨트롤을 제어하고 워크플로의 모델 변경 내용에 따라 호스트가 도구 상자 컨트롤에 적절한 변경 내용을 적용하도록 할 수 있습니다.그러나 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서는 사용자가 도구 상자를 제어하지 않으므로 도구 상자 내용을 수정하려면 인터페이스가 필요합니다.`IActivityToolboxService`가 해당 인터페이스입니다.  
  
 API는 다음 네 가지 메서드를 제공합니다.  
  
```  
public interface IActivityToolboxService   
{   
        void AddCategory(string categoryName);   
        void RemoveCategory(string categoryName);   
        void AddItem(string qualifiedTypeName, string categoryName);   
        void RemoveItem(string qualifiedTypeName, string categoryName);   
        IList<string> EnumCategories();   
        IList<string> EnumItems(string categoryName);   
}  
```  
  
#### 샘플을 설치, 빌드 및 실행하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 사용하여 WorkflowSimulator.sln 솔루션 파일을 엽니다.  
  
2.  Ctrl\+Shift\+B를 눌러 솔루션을 빌드합니다.  
  
3.  Workflow.xaml 파일을 엽니다.  
  
4.  도구 상자에서 **CustomActivity**를 끌어서 놓는 방법으로 추가합니다.추가 활동인 **Assign**과 함께 **새 WF 범주**라는 추가 도구 상자 범주가 있습니다.  
  
5.  이제 다른 활동을 끌어 와서 **CustomActivity**의 선택을 취소합니다.  
  
6.  이제 도구 상자 아래의 **새 WF 범주**에서 **Assign** 항목이 제거됩니다.또한 범주에 더 이상 남은 항목이 없으므로 범주도 제거됩니다.  
  
7.  **CustomActivity**를 다시 선택하고 범주를 선택합니다. 그러면 **Assign** 활동이 다시 추가됩니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\IActivityToolboxService`