---
title: Dynamic 인수
ms.date: 03/30/2017
ms.assetid: 122ad479-d306-4602-a943-5aefe711329d
ms.openlocfilehash: 5c00b9678191e4e88e9e41380d6b10be39684b3b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517980"
---
# <a name="dynamic-arguments"></a>Dynamic 인수
이 샘플에서는 활동 작성자가 아니라 활동 소비자에 의해 인수가 정의되는 활동을 구현하는 방법을 보여 줍니다. 이를 위해 런타임에서 활동의 메타데이터가 생성되는 방식을 재정의합니다.  
  
## <a name="sample-details"></a>샘플 세부 정보  
 실행 전 런타임에서는 활동 형식의 공용 멤버를 검사하고 자동으로 인수, 변수, 자식 활동 및 활동 대리자를 활동 메타데이터의 일부로 선언하여 활동에 대한 설명을 작성합니다. 이를 통해 런타임에서는 워크플로가 올바르게 생성되도록 할 뿐 아니라 런타임 관계 및 수명 규칙을 관리합니다. 일반적으로 활동 작성자는 <xref:System.Activities.Argument>에서 파생된 활동 형식에 공용 멤버를 지정하여 활동의 인수를 정의합니다. 런타임에서는 <xref:System.Activities.Argument>에서 파생된 각 공용 멤버에 대해 <xref:System.Activities.RuntimeArgument>를 만들고 이를 해당 멤버에 대해 사용자가 제공한 인수 집합에 바인딩합니다. 그러나 일부 경우에는 활동의 소비자가 인수 집합을 결정하는 구성을 제공합니다. 활동 작성자는 <xref:System.Activities.Activity.CacheMetadata%2A>를 재정의하여 활동과 관련된 인수 집합을 비롯한 활동 메타데이터를 작성하는 방식을 사용자 지정합니다.  
  
 이 샘플에서는 메서드를 호출하는 활동에 대해 동적으로 인수 목록을 작성하는 방법을 보여 줍니다. 활동 소비자는 호출할 형식 및 메서드 이름과 함께 해당 메서드에 전달할 인수 컬렉션을 지정합니다.  
  
> [!NOTE]
>  이 샘플의 목적은 <xref:System.Activities.CodeActivity.CacheMetadata%2A>의 재정의 방법과 <xref:System.Activities.RuntimeArgument>의 사용 방법을 보여 주는 것입니다. 이 활동이 호출할 수 있는 메서드 종류와 관련하여 주의해야 할 사항이 몇 가지 있습니다. 예를 들어 이 활동은 제네릭 또는 매개 변수 배열과 함께 사용할 수 없습니다. .NET Framework에서 제공되는 <xref:System.Activities.Statements.InvokeMethod> 활동은 이와 같은 여러 경우를 처리합니다.  
  
 `MethodInvoke` 활동은 <xref:System.Activities.CodeActivity.CacheMetadata%2A>를 재정의하고, <xref:System.Activities.RuntimeArgument>를 만들어 메서드 호출 결과를 처리함으로써 작업을 시작합니다. 또한 이 <xref:System.Activities.RuntimeArgument>를 공개적으로 설정 가능한 <xref:System.Activities.OutArgument>라는 `Result`에 바인딩합니다. `MethodInvoke.Result`가 `null`이면 런타임에서는 해당 형식의 기본 식으로 구성된 <xref:System.Activities.OutArgument>로 이를 자동으로 채웁니다. 따라서 활동 작성자는 인수 속성이 `null`인지 여부를 확인할 필요가 전혀 없습니다.  
  
 그런 다음 <xref:System.Activities.CodeActivity.CacheMetadata%2A> 재정의는 사용자가 제공한 `MethodInfo` 및 `MethodName`에서 호출할 때 사용하는 `TargetType`를 확인합니다. `DetermineMethodInfo` 메서드는 모든 구성 오류를 유효성 검사 오류로 보고할 수 있도록 <xref:System.Activities.CodeActivityMetadata> 재정의에 전달된 <xref:System.Activities.CodeActivity.CacheMetadata%2A> 매개 변수를 사용하며, 이를 위해 `metadata.AddValidationError`를 호출합니다.  
  
 `MethodInfo`가 설정된 후 이 샘플에서는 `MethodInfo` 매개 변수를 반복합니다. 또한 각 매개 변수에 대해 <xref:System.Activities.RuntimeArgument>를 만들고 이를 `Parameters` 속성에서 사용자가 제공한 컬렉션의 해당 인수에 바인딩합니다. 마지막으로는 <xref:System.Activities.RuntimeArgument>을 호출하여 `metadata.SetArgumentsCollection`의 컬렉션을 활동과 연결합니다.  
  
 <xref:System.Activities.RuntimeArgument> 또는 사용자 제공 인수의 경우나 `resultArgument` 컬렉션의 경우와 같이 `Parameters`를 사용하여 인수를 확인할 수 있습니다.  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 DynamicArguments.sln 파일을 엽니다.  
  
2.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
3.  Ctrl+F5를 눌러 솔루션을 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\DynamicArguments`