---
title: 이 첫 번째 문은 &#39;Sub New&#39; 에 대 한 호출 이어야 합니다 &#39;MyBase.New&#39; 또는 &#39;MyClass.New&#39; (No 액세스할 수 있는 매개 변수가 없는 생성자)
ms.date: 07/20/2015
f1_keywords:
- bc30148
- vbc30148
helpviewer_keywords:
- BC30148
ms.assetid: 4426e8fc-cb39-4eb8-ba95-503cd32fcc89
ms.openlocfilehash: 3b24385932700a4843ae295bc82ef9529cc86b9b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33589462"
---
# <a name="first-statement-of-this-39sub-new39-must-be-a-call-to-39mybasenew39-or-39myclassnew39-no-accessible-constructor-without-parameters"></a>이 첫 번째 문은 &#39;Sub New&#39; 에 대 한 호출 이어야 합니다 &#39;MyBase.New&#39; 또는 &#39;MyClass.New&#39; (No 액세스할 수 있는 매개 변수가 없는 생성자)
때문에이 ' Sub n e w '의 첫째 문은 'MyBase.New' 또는 'MyClass.New'에 대 한 호출 이어야 합니다 기본 클래스\<basename >'의 '\<derivedname >' 인수 없이 호출 될 수 있는 액세스 가능한 ' Sub n가 없습니다.  
  
 파생된 클래스에서 모든 생성자는 기본 클래스 생성자를 호출 해야 합니다 (`MyBase.New`). 기본 클래스에 있는 경우 파생된 클래스에 액세스할 수 있는 매개 변수가 없는 생성자 `MyBase.New` 자동으로 호출 될 수 있습니다. 그렇지 않은 경우 매개 변수를 사용 하는 기본 클래스 생성자를 호출 해야 하 고 자동으로 수행할 수 없습니다. 이 경우 모든 파생된 클래스 생성자의 첫 번째 문 기본 클래스에는 매개 변수가 있는 생성자를 호출 하거나 기본 클래스 생성자를 호출 하는 파생된 클래스에서 다른 생성자를 호출 해야 합니다.  
  
 **오류 ID:** BC30148  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   호출 하거나 `MyBase.New` 필수 매개 변수를 제공 하거나 이러한 호출 피어 생성자를 호출 합니다.  
  
     예를 들어 기본 클래스 생성자로 선언 된 `Public Sub New(ByVal index as Integer)`, 첫 번째 문으로 파생 된 클래스 생성자 일 수 있습니다 `MyBase.New(100)`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [상속 기본 사항](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
