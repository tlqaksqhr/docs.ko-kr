---
title: "Visual Basic의 액세스 수준"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- members [Visual Basic], accessing in Visual Basic
- Friend access modifier
- access levels, declared elements
- access levels
- access modifiers
- Public access modifier
- Protected access modifier
- Protected Friend access modifier
- Private access modifier
- declared elements [Visual Basic], access level
ms.assetid: 6e06c1ab-fd78-47f0-83a8-1152780b5e1a
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 87e43ac7e813cece1179bdaf24c86fa62adcb438
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="access-levels-in-visual-basic"></a>Visual Basic의 액세스 수준
*액세스 수준* 의 선언 된 요소에 액세스할 수 정도, 즉, 있는 코드를 읽거나 쓰려고 합니다. 이 요소 자체를 선언한 방법 뿐만 아니라 요소의 컨테이너의 액세스 수준을 통해 결정 됩니다. 것까지 포함 하는 요소에 액세스할 수 없는 코드에 액세스할 수 없는 모든 포함 된 요소로 선언 `Public`합니다. 예를 들어 한 `Public` 변수에 `Private` 구조에서가 아니라 서 구조를 포함 하는 클래스 내부에서 액세스할 수 해당 클래스 외부 합니다.  
  
## <a name="public"></a>공용  
 [공용](../../../../visual-basic/language-reference/modifiers/public.md) 선언문에서 키워드는 같은 프로젝트의 코드, 프로젝트를 참조 하는 다른 프로젝트 및 프로젝트에서 빌드된 어셈블리에서 요소에 액세스할 수 있는지 지정 합니다. 다음 코드 예제를 보여 줍니다. `Public` 선언 합니다.  
  
```  
Public Class classForEverybody  
```  
  
 사용할 수 있습니다 `Public` 모듈, 인터페이스 또는 네임 스페이스 수준 에서만. 즉, 소스 파일 또는 네임 스페이스의 또는 인터페이스, 모듈, 클래스 또는 구조체 내에 있지만 프로시저 수준에서 공용 요소를 선언할 수 있습니다.  
  
## <a name="protected"></a>보호됨  
 [Protected](../../../../visual-basic/language-reference/modifiers/protected.md) 선언문에서 키워드 지정 요소는이 클래스 로부터 파생 된 클래스 또는 동일한 클래스 내에서 에서만 액세스할 수 있습니다. 다음 코드 예제를 보여 줍니다. `Protected` 선언 합니다.  
  
```  
Protected Class classForMyHeirs  
```  
  
 사용할 수 있습니다 `Protected` 클래스에만 수준 선언할 때 클래스의 멤버입니다. 즉, 수준이 아닌 인터페이스, 모듈, 구조체 또는 프로시저 내부에서 실행 되거나 소스 파일 또는 네임 스페이스의 클래스에는 보호 된 요소를 선언할 수 있습니다.  
  
## <a name="friend"></a>Friend  
 [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) 선언문에서 키워드에서가 아니라 하지만 동일한 어셈블리 내에서 요소에 액세스할 수 있다는 지정 어셈블리 외부에 있습니다. 다음 코드 예제를 보여 줍니다. `Friend` 선언 합니다.  
  
```  
Friend stringForThisProject As String  
```  
  
 사용할 수 있습니다 `Friend` 모듈, 인터페이스 또는 네임 스페이스 수준 에서만. 즉, 소스 파일 또는 네임 스페이스의 또는 인터페이스, 모듈, 클래스 또는 구조체 내에 있지만 프로시저 수준에서 friend 요소를 선언할 수 있습니다.  
  
## <a name="protected-friend"></a>Protected Friend  
 `Protected` 및 `Friend` 선언문에서 키워드 또는 파생 된 클래스에서 내에서 요소를 액세스할 수 있도록 지정할 동일한 어셈블리 또는 둘 다 합니다. 다음 코드 예제를 보여 줍니다. `Protected Friend` 선언 합니다.  
  
```  
Protected Friend stringForProjectAndHeirs As String  
```  
  
 사용할 수 있습니다 `Protected Friend` 클래스에만 수준 선언할 때 클래스의 멤버입니다. 즉, protected friend 클래스에 있지만 수준이 아닌 인터페이스, 모듈, 구조체 또는 프로시저 내부에서 실행 되거나 소스 파일 또는 네임 스페이스의 요소를 선언할 수 있습니다.  
  
## <a name="private"></a>Private  
 [개인](../../../../visual-basic/language-reference/modifiers/private.md) 요소에 동일한 모듈, 클래스 또는 구조체 내 에서만 액세스할 수 있다는 선언문에서 키워드를 지정 합니다. 다음 코드 예제를 보여 줍니다. `Private` 선언 합니다.  
  
```  
Private numberForMeOnly As Integer  
```  
  
 `Private`는 모듈 수준에서만 사용할 수 있습니다. 즉, 모듈, 클래스 또는 구조체 내 있지만 소스 파일 또는 인터페이스 내 또는 프로시저에서 네임 스페이스의 수준이 아닌 개인 요소를 선언할 수 있습니다.  
  
 모듈 수준에서의 `Dim` 문을 액세스 수준 키워드 없이 해당 하는 `Private` 선언 합니다. 하지만, 사용 하도록 필요할 수 있습니다는 `Private` 키워드 코드를 읽고 해석 하기 쉽게 수행할 수 있도록 합니다.  
  
## <a name="access-modifiers"></a>액세스 한정자  
 액세스 수준을 지정 하는 키워드 라고 *액세스 한정자*합니다. 다음 표에서 액세스 한정자를 비교 합니다.  
  
|액세스 한정자|부여 된 액세스 수준|이 액세스 수준으로 선언할 수 요소|이 한정자를 사용할 수 있는 선언 컨텍스트|  
|---------------------|--------------------------|-----------------------------------------------------|----------------------------------------------------------------|  
|`Public`|무제한:<br /><br /> Public 요소를 볼 수 있습니다. 있는 모든 코드에 액세스할 수 있습니다.|인터페이스<br /><br /> 모듈<br /><br /> 클래스<br /><br /> 구조체<br /><br /> 구조체 멤버<br /><br /> 절차<br /><br /> 속성<br /><br /> 멤버 변수<br /><br /> 상수<br /><br /> 열거형<br /><br /> 이벤트<br /><br /> 외부 선언<br /><br /> 대리자|소스 파일<br /><br /> 네임스페이스<br /><br /> 인터페이스<br /><br /> 모듈<br /><br /> 클래스<br /><br /> 구조체|  
|`Protected`|파생:<br /><br /> 요소에 액세스할 수는 보호 된 요소 또는 여기에서 파생 된 클래스를 선언 하는 클래스의 코드에서|인터페이스<br /><br /> 클래스<br /><br /> 구조체<br /><br /> 절차<br /><br /> 속성<br /><br /> 멤버 변수<br /><br /> 상수<br /><br /> 열거형<br /><br /> 이벤트<br /><br /> 외부 선언<br /><br /> 대리자|클래스|  
|`Friend`|어셈블리:<br /><br /> Friend 요소에 액세스할 수를 선언 하는 어셈블리의 코드에서|인터페이스<br /><br /> 모듈<br /><br /> 클래스<br /><br /> 구조체<br /><br /> 구조체 멤버<br /><br /> 절차<br /><br /> 속성<br /><br /> 멤버 변수<br /><br /> 상수<br /><br /> 열거형<br /><br /> 이벤트<br /><br /> 외부 선언<br /><br /> 대리자|소스 파일<br /><br /> 네임스페이스<br /><br /> 인터페이스<br /><br /> 모듈<br /><br /> 클래스<br /><br /> 구조체|  
|`Protected` `Friend`|공용 구조체에 `Protected` 및 `Friend`:<br /><br /> 동일한 클래스 또는 protected friend 요소 또는 요소의 클래스에서 파생 된 클래스 내에서 동일한 어셈블리에서 코드를 액세스할 수 있습니다.|인터페이스<br /><br /> 클래스<br /><br /> 구조체<br /><br /> 절차<br /><br /> 속성<br /><br /> 멤버 변수<br /><br /> 상수<br /><br /> 열거형<br /><br /> 이벤트<br /><br /> 외부 선언<br /><br /> 대리자|클래스|  
|`Private`|선언 컨텍스트.<br /><br /> 요소에 액세스할 수 포함 된 형식 내에서 코드를 포함 하 여 private 요소를 선언 하는 형식 코드|인터페이스<br /><br /> 클래스<br /><br /> 구조체<br /><br /> 구조체 멤버<br /><br /> 절차<br /><br /> 속성<br /><br /> 멤버 변수<br /><br /> 상수<br /><br /> 열거형<br /><br /> 이벤트<br /><br /> 외부 선언<br /><br /> 대리자|모듈<br /><br /> 클래스<br /><br /> 구조체|  
  
## <a name="see-also"></a>참고 항목  
 [Dim 문](../../../../visual-basic/language-reference/statements/dim-statement.md)  
 [정적](../../../../visual-basic/language-reference/modifiers/static.md)  
 [선언 요소 이름](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [선언된 요소 참조](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [선언 요소의 특징](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [Visual Basic의 수명](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)  
 [Visual Basic의 범위](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)  
 [방법: 변수의 사용 가능성 제어](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-availability-of-a-variable.md)  
 [변수](../../../../visual-basic/programming-guide/language-features/variables/index.md)  
 [변수 선언](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
