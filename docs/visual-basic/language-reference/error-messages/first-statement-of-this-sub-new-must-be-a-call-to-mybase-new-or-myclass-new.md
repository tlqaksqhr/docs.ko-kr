---
title: "이 &#39;의 첫 번째 문 새 하위 &#39; 에 대 한 호출 &#39; 이어야 합니다. MyBase.New &#39; 또는 &#39; MyClass.New &#39; (매개 변수 없이 액세스할 수 있는 생성자 없음)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30148
- vbc30148
helpviewer_keywords: BC30148
ms.assetid: 4426e8fc-cb39-4eb8-ba95-503cd32fcc89
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1065643e1f6c868092fbad839af0dbbd33afaf01
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="first-statement-of-this-39sub-new39-must-be-a-call-to-39mybasenew39-or-39myclassnew39-no-accessible-constructor-without-parameters"></a>이 &#39;의 첫 번째 문 새 하위 &#39; 에 대 한 호출 &#39; 이어야 합니다. MyBase.New &#39; 또는 &#39; MyClass.New &#39; (매개 변수 없이 액세스할 수 있는 생성자 없음)
때문에이 ' Sub n e w '의 첫째 문은 'MyBase.New' 또는 'MyClass.New'에 대 한 호출 이어야 합니다 기본 클래스\<basename >'의 '\<derivedname >' 인수 없이 호출 될 수 있는 액세스 가능한 ' Sub n가 없습니다.  
  
 파생된 클래스에서 모든 생성자는 기본 클래스 생성자를 호출 해야 합니다 (`MyBase.New`). 기본 클래스에 있는 경우 파생된 클래스에 액세스할 수 있는 매개 변수가 없는 생성자 `MyBase.New` 자동으로 호출 될 수 있습니다. 그렇지 않은 경우 매개 변수를 사용 하는 기본 클래스 생성자를 호출 해야 하 고 자동으로 수행할 수 없습니다. 이 경우 모든 파생된 클래스 생성자의 첫 번째 문 기본 클래스에는 매개 변수가 있는 생성자를 호출 하거나 기본 클래스 생성자를 호출 하는 파생된 클래스에서 다른 생성자를 호출 해야 합니다.  
  
 **오류 ID:** BC30148  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   호출 하거나 `MyBase.New` 필수 매개 변수를 제공 하거나 이러한 호출 피어 생성자를 호출 합니다.  
  
     예를 들어 기본 클래스 생성자로 선언 된 `Public Sub New(ByVal index as Integer)`, 첫 번째 문으로 파생 된 클래스 생성자 일 수 있습니다 `MyBase.New(100)`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [상속 기본 사항](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
