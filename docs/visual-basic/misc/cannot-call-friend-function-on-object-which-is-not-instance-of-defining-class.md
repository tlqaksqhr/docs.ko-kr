---
title: 클래스 정의 인스턴스가 아닌 개체에서 friend 함수를 호출할 수 없습니다.
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID97
ms.assetid: b9d821f0-8565-4f15-bb35-184789c69662
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2f1ac1ea14efb0cdf0d8ca03257e4da33d35e368
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="cannot-call-friend-function-on-object-which-is-not-an-instance-of-defining-class"></a>클래스 정의 인스턴스가 아닌 개체에서 friend 함수를 호출할 수 없습니다.
크로스 프로세스 또는 크로스 스레드로 클래스의 `Friend` 프로시저를 호출하려고 했거나 `Friend` 속성 또는 메서드에 액세스하려고 했습니다. `Friend` 프로시저는 클래스 외부에 있지만 클래스가 정의되는 프로젝트의 일부인 모듈에서 호출할 수 있습니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   클래스가 정의되는 프로젝트의 일부인 모듈에서 프로시저를 호출하거나 액세스하고 있는지 확인합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Friend](../../visual-basic/language-reference/modifiers/friend.md)
