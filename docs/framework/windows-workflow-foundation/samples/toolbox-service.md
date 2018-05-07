---
title: 도구 상자 서비스
ms.date: 03/30/2017
ms.assetid: 742212d0-445e-41ed-9739-9ee848ce7f1b
ms.openlocfilehash: 0b3ea56d28d202bd8356fea1783b6675a708631d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="toolbox-service"></a>도구 상자 서비스
이 샘플에서는 워크플로 컨텍스트를 기반으로 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 도구 상자 활동을 업데이트하는 방법을 보여 줍니다. 이 샘플에는 사용자 지정 활동이 선택되었는지 여부에 따라 도구 상자 내용을 변경하는 워크플로가 포함되어 있습니다.  
  
## <a name="discussion"></a>토론  
 워크플로를 작성할 때 고객은 일반적으로 도구 상자가 상황에 맞게 표시되기를 원합니다.  예를 들어 사용자가 워크플로에 특정 활동을 추가하는 경우 도구 상자에 몇 가지 추가 활동이 표시되도록 할 수 있습니다. 워크플로에서 활동을 제거하는 경우 도구 상자는 도메인 요구 사항을 기반으로 적절하게 응답해야 합니다.  
  
 다시 호스트된 Workflow Designer에서 도구 상자 컨트롤을 제어하고 워크플로의 모델 변경 내용에 따라 호스트가 도구 상자 컨트롤에 적절한 변경 내용을 적용하도록 할 수 있습니다. 그러나 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서는 사용자가 도구 상자를 제어하지 않으므로 도구 상자 내용을 수정하려면 인터페이스가 필요합니다. `IActivityToolboxService`가 해당 인터페이스입니다.  
  
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
  
#### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 사용하여 WorkflowSimulator.sln 솔루션 파일을 엽니다.  
  
2.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
3.  Workflow.xaml 파일을 엽니다.  
  
4.  추가 **CustomActivity** 끌어서 도구 상자에서 삭제 합니다. 추가 도구 상자 범주가 라는: **새 WF 범주** 추가 활동이 포함 된 **할당**합니다.  
  
5.  선택 취소 합니다. 이제는 **CustomActivity** 다른 활동을 끌어 여 합니다.  
  
6.  항목 **할당** 범주의 **새 WF 범주** 의 도구 상자에서 제거 됩니다. 또한 범주에 더 이상 남은 항목이 없으므로 범주도 제거됩니다.  
  
7.  선택 된 **CustomActivity** 다시와 범주 및 **할당** 활동이 다시 추가 됩니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\IActivityToolboxService`
