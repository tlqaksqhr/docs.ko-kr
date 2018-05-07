---
title: Advanced Policy
ms.date: 03/30/2017
ms.assetid: 75a22c88-5e54-4ae8-84cb-fbb22a612f0a
ms.openlocfilehash: 81cf2fb428833d4ca8cccf197011b69f2ccf3108
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="advanced-policy"></a>Advanced Policy
이 샘플은 Simple Policy 샘플의 확장입니다. Simple Policy 예제의 가계 할인 규칙과 기업 할인 규칙 이외에 새로운 규칙이 몇 가지 추가되었습니다.  
  
 첫째, 고가치 규칙이 추가되어 값이 큰 주문에 대해 더 큰 할인을 제공합니다. 이 규칙은 할인 필드를 덮어쓰고 가계 할인 규칙과 기업 할인 규칙보다 우선적으로 적용되도록 이전 두 규칙보다 작은 우선 순위 값이 부여되었습니다.  
  
 둘째, 합계 계산 규칙이 추가되어 할인 수준을 기반으로 합계를 계산합니다. 워크플로 활동에 정의된 메서드를 참조하는 방법과 Else 작업 사용 방법을 보여 줍니다. 이 규칙은 할인 필드가 변경될 때마다 확인되는 연결 동작을 보여 주기도 합니다. 뿐만 아니라 CalculateTotal 메서드의 RuleWriteAttribute를 사용하여 메서드 특성 지정도 보여 줍니다. 이로 인해 이 규칙의 영향을 받는 규칙(ErrorTotalRule)은 메서드가 실행될 때마다 재확인됩니다.  
  
 셋째, 오류를 감지하는 규칙이 추가되었습니다(이 경우에는 합계가 0보다 작을 때). 오류가 감지되면 정책 실행이 중지됩니다.  
  
 이러한 규칙 추가 외에도, 각 규칙에 `Console.Writeline` 호출이 작업으로 추가되어 규칙 실행 상황을 보기 쉬울 뿐만 아니라 참조된 형식의 정적 메서드에 액세스할 수 있음을 보여 줍니다. 사용자는 추적을 사용하여 실행된 규칙을 확인할 수도 있습니다.  
  
 이 샘플에 사용된 규칙은 다음과 같습니다.  
  
 **ResidentialDiscountRule:**  
  
 IF OrderValue > 500 AND CustomerType = Residential  
  
 THEN Discount = 5%  
  
 **BusinessDiscountRule:**  
  
 IF OrderValue > 10000 AND CustomerType = Business  
  
 THEN Discount = 10%  
  
 **HighValueDiscountRule:**  
  
 IF OrderValue > 20000  
  
 THEN Discount = 15%  
  
 **TotalRule:**  
  
 IF Discount > 0  
  
 THEN CalculateTotal(OrderValue, Discount)  
  
 ELSE Total = OrderValue  
  
 **ErrorTotalRule:**  
  
 IF 총 \< 0  
  
 THEN Error = "Fired ErrorTotalRule"; Halt  
  
 규칙 확인 및 실행은 추적을 통해서도 확인할 수 있습니다.  
  
### <a name="to-build-the-sample"></a>이 샘플을 빌드하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 솔루션을 엽니다.  
  
2.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
3.  Ctrl+F5를 눌러 디버깅 없이 솔루션을 실행합니다.  
  
### <a name="to-run-the-sample"></a>이 샘플을 실행하려면  
  
-   SDK 명령 프롬프트 창에서 샘플의 주 폴더 아래에 있는 AdvancedPolicy\bin\debug 폴더 또는 AdvancedPolicy\bin 폴더(Visual Basic 버전 샘플의 경우)의 .exe 파일을 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\Policy\AdvancedPolicy`  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Workflow.Activities.Rules.RuleSet>  
 <xref:System.Workflow.Activities.PolicyActivity>  
 [단순 정책](../../../../docs/framework/windows-workflow-foundation/samples/simple-policy.md)
