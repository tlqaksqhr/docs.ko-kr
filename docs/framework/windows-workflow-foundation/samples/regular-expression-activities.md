---
title: "정규식 활동"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b8f24694-49db-4339-92ec-014e3d4ae63b
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: edeb55f25abf9e6f22ebfe1d0ea63eb07ba0f203
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="regular-expression-activities"></a>정규식 활동
이 샘플에서는 <xref:System.Text.RegularExpressions> 네임스페이스의 정규식 기능을 노출하는 활동 집합을 만드는 방법을 보여 줍니다. 이러한 사용자 지정 활동은 워크플로 응용 프로그램 내에서 사용할 수 있습니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]정규식, 참조 [N:System.Text.RegularExpressions](http://go.microsoft.com/fwlink/?LinkId=150434) Namespace입니다.  
  
 다음 표에는 이 샘플의 사용자 지정 활동에 대한 자세한 설명이 나와 있습니다.  
  
|동작|설명|  
|--------------|-----------------|  
|IsMatch|입력 문자열에서 정규식에 일치하는 항목을 찾았는지 여부를 나타냅니다.|  
|요청 내용|입력 문자열에서 정규식의 모든 항목을 검색하고 일치하는 항목을 모두 반환합니다.|  
|Replace|지정된 입력 문자열 내에서 정규식 패턴에 일치하는 문자열을 지정된 대체 문자열로 바꿉니다.|  
  
## <a name="ismatch"></a>IsMatch  
 `IsMatch` 사용자 지정 활동은 `true` 문자열 속성에서 `Input` 속성에 지정된 정규식에 일치하는 항목을 찾은 경우 `Pattern`를 반환합니다. 이 활동은 <xref:System.Activities.CodeActivity%601>에서 파생되며 <xref:System.Activities.CodeActivity%601.Execute%2A> 메서드 내에서 <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> 메서드를 호출합니다.  
  
 다음 표에서는 `IsMatch` 사용자 지정 활동의 속성과 반환 값을 설명합니다.  
  
|속성 또는 반환 값|설명|  
|------------------------------|-----------------|  
|Pattern(필수)|검색에 사용할 정규식입니다.|  
|Input(필수)|검색할 입력 문자열입니다.|  
|RegexOptions|비트 OR 조합 [RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446) 열거형 값입니다.|  
|반환 값|제공된 패턴에 일치하는 항목을 입력에서 찾으면 `true`이고, 그렇지 않으면 `false`입니다.|  
  
 다음 코드 예제에서는 `IsMatch` 사용자 지정 활동을 사용하는 방법을 보여 줍니다.  
  
```  
new IsMatch  
{  
    Pattern = new InArgument<string>( @"^-?\d+(\.\d{2})?$"),  
    Input = "20.00",  
};  
```  
  
## <a name="matches"></a>요청 내용  
 `Matches` 사용자 지정 활동은 입력 문자열에서 정규식의 모든 항목을 검색하고 일치하는 항목을 모두 반환합니다. 이 활동은 <xref:System.Activities.CodeActivity%601>에서 파생되며 <xref:System.Activities.CodeActivity%601.Execute%2A> 메서드 내에서 <xref:System.Text.RegularExpressions.Regex.Matches%2A> 메서드를 호출합니다.  
  
 다음 표에서는 `IsMatch` 사용자 지정 활동의 속성과 반환 값을 설명합니다.  
  
|속성 또는 반환 값|설명|  
|------------------------------|-----------------|  
|Pattern(필수)|검색에 사용할 정규식입니다.|  
|Input(필수)|검색할 입력 문자열입니다.|  
|RegexOptions|비트 OR 조합 [RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446) 열거형 값입니다.|  
|반환 값|일치하는 항목의 컬렉션이 포함된 <xref:System.Text.RegularExpressions.MatchCollection>입니다.|  
  
 다음 코드 예제에서는 `Matches` 사용자 지정 활동을 사용하는 방법을 보여 줍니다.  
  
```  
new Matches  
{  
    Pattern = @"\b(?<word>\w+)\s+(\k<word>)\b",  
    Input = "The quick brown fox  fox jumped over over the lazy dog dog.",  
};  
```  
  
## <a name="replace"></a>Replace  
 `Replace` 사용자 지정 활동은 입력 문자열을 검색하고 지정된 정규식에 일치하는 모든 문자열을 대체 문자열로 바꿉니다. 이 활동은 <xref:System.Activities.CodeActivity%601>에서 파생되며 <xref:System.Activities.CodeActivity%601.Execute%2A> 메서드 내에서 <xref:System.Text.RegularExpressions.Regex.Replace%2A> 메서드를 호출합니다.  
  
 다음 표에서는 `Replace` 사용자 지정 활동의 속성과 반환 값을 설명합니다.  
  
|속성 또는 반환 값|설명|  
|------------------------------|-----------------|  
|Pattern(필수)|검색에 사용할 정규식입니다.|  
|Input(필수)|검색할 입력 문자열입니다.|  
|Replacement|대체 문자열입니다.<br /><br /> `Replacement`를 지정한 경우 `MatchEvaluator` 속성이 무시됩니다. `Replacement` 또는 `MatchEvaluator` 속성 중 하나는 반드시 설정해야 합니다.|  
|MatchEvaluator|각 항목의 일치 여부를 조사하고 원래 일치 문자열 또는 대체 문자열을 반환하는 사용자 지정 메서드입니다.<br /><br /> `Replacement`를 지정한 경우 `MatchEvaluator` 속성이 무시됩니다. `Replacement` 또는 `MatchEvaluator` 속성 중 하나는 반드시 설정해야 합니다.|  
|RegexOptions|비트 OR 조합 [RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446) 열거형 값입니다.|  
|반환 값|일치하는 항목의 컬렉션이 포함된 <xref:System.Text.RegularExpressions.MatchCollection>입니다.|  
  
 다음 코드 예제에서는 `Replace` 사용자 지정 활동을 사용하는 방법을 보여 줍니다.  
  
```  
// Using the replacement string.  
new Replace  
{  
    Pattern = @"\bWorld\b",  
    Input = "Hello World! This is a wonderful World",  
    Replacement = "Universe"  
};  
  
// Using a match evaluator.  
new Replace  
{  
    Pattern = new InArgument<string>(pattern),  
    Input = new InArgument<string>(input),  
    MatchEvaluator = new MatchEvaluator(CapText)                  
};  
```  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 RegexActivities.sln 솔루션 파일을 엽니다.  
  
2.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
3.  Ctrl+F5를 눌러 솔루션을 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Regex`  
  
## <a name="see-also"></a>참고 항목
