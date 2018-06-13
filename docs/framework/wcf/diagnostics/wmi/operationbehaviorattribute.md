---
title: OperationBehaviorAttribute
ms.date: 03/30/2017
ms.assetid: 8c9b0755-9e83-411f-bdcb-61a586022797
ms.openlocfilehash: 4f731d146885265d9f956c182f1bebdba5db924b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33486873"
---
# <a name="operationbehaviorattribute"></a>OperationBehaviorAttribute
OperationBehaviorAttribute  
  
## <a name="syntax"></a>구문  
  
```  
class OperationBehaviorAttribute : Behavior  
{  
  boolean AutoDisposeParameters;  
  string Impersonation;  
  string ReleaseInstanceMode;  
  boolean TransactionAutoComplete;  
  boolean TransactionScopeRequired;  
};  
```  
  
## <a name="methods"></a>메서드  
 OperationBehaviorAttribute 클래스는 메서드를 정의하지 않습니다.  
  
## <a name="properties"></a>속성  
 OperationBehaviorAttribute 클래스에는 다음과 같은 속성이 있습니다.  
  
### <a name="autodisposeparameters"></a>AutoDisposeParameters  
 데이터 형식: boolean  
  
 액세스 형식: 읽기 전용  
  
 매개 변수에 대한 자동 삭제 기능 상태입니다.  
  
### <a name="impersonation"></a>가장  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 작업에서 지원하는 호출자의 가장 수준을 나타냅니다.  
  
### <a name="releaseinstancemode"></a>ReleaseInstanceMode  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 작업 과정에서 개체를 재활용하기 위해 호출하는 시점을 나타냅니다.  
  
### <a name="transactionautocomplete"></a>TransactionAutoComplete  
 데이터 형식: boolean  
  
 액세스 형식: 읽기 전용  
  
 처리되지 않은 예외가 발생하지 않을 때 현재 트랜잭션을 자동으로 커밋할지 여부를 나타냅니다.  
  
### <a name="transactionscoperequired"></a>TransactionScopeRequired  
 데이터 형식: boolean  
  
 액세스 형식: 읽기 전용  
  
 작업에서 트랜잭션이 필요한지 여부를 나타냅니다.  
  
## <a name="requirements"></a>요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|-----------------------------------|  
|네임스페이스|root\ServiceModel에 정의되어 있습니다.|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.OperationBehaviorAttribute>
