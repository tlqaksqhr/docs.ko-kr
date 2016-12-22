---
title: "Constants Overview (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "constants"
ms.assetid: 29016fe8-78b3-4dc8-90b8-1cfec2fa8ac9
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Constants Overview (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

상수는 숫자나 문자열 대신 사용되며 변경되지 않는 의미 있는 이름입니다.  상수는 이름이 의미하는 것처럼 응용 프로그램을 실행하는 동안 동일하게 유지되는 값을 저장합니다.  상수를 사용하면 코드의 가독성을 크게 향상시키고 코드를 손쉽게 유지 관리할 수 있습니다.  다시 나타나는 값을 포함하거나, 기억하기 어렵거나 의미가 명확하지 않은 특정 숫자에 따라 달라지는 코드에 상수를 사용합니다.  
  
## 상수 만들기 및 사용 방법  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에는 인쇄 및 표시용으로 주로 사용되는 미리 정의된 상수가 다양하게 포함되어 있습니다.  변수 이름을 만들 때와 같은 방법으로 `Const` 문을 사용하여 고유의 상수를 만들 수도 있습니다.  `Option Strict`가 `On`이면 상수 형식을 명시적으로 선언해야 합니다.  
  
 상수의 범위는 이름을 한정하지 않고도 해당 상수를 참조할 수 있는 모든 코드의 집합을 나타내며 같은 위치에 선언된 변수의 범위와 동일합니다.  특정 프로시저 범위 내에 존재하는 상수를 만들려면 해당 프로시저 내부에서 상수를 선언하십시오.  응용 프로그램 전체에서 사용할 수 있는 상수를 만들려면 클래스의 선언 섹션에서 `Public` 키워드를 사용하여 상수를 선언합니다.  
  
> [!NOTE]
>  상수는 어떤 면에서는 변수와 비슷하지만 수정하거나 새 값을 할당할 수 없다는 점에서 변수와는 다릅니다.  
  
 코드에 사용하는 상수는 컨트롤 또는 구성 요소의 개체 모델에서 정의된 상수이거나 사용자가 직접 만든 사용자 정의 상수일 수 있습니다.  
  
## 컴파일 타임 및 런타임 상수  
 컴파일 타임 상수는 코드가 컴파일될 때 계산되고 런타임 상수는 응용 프로그램이 실행되는 동안에만 계산됩니다.  컴파일 타임 상수는 응용 프로그램 실행에 관계없이 항상 같은 값을 갖지만 런타임 상수는 매번 변경될 수 있습니다.  컴파일 타임 상수는 배열 범위, case 식 또는 열거자 이니셜라이저 등의 경우에 필요합니다.  
  
## 단원 내용  
  
|||  
|-|-|  
|정의|용어|  
|[How to: Declare A Constant](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)|`Const` 문을 사용하여 상수를 선언하고 상수 값을 설정하여 의미 있는 이름을 값에 할당하는 방법에 대해 설명합니다.|  
|[User\-Defined Constants](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)|범위 지정에 대한 정보를 포함하여 사용자 자신의 상수를 만드는 방법과 순환 참조를 피하는 방법에 대해 설명합니다.|  
|[Constant and Literal Data Types](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)|`Option Explicit`가 OFF인 경우 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러가 상수를 초기화하는 방법에 대해 설명합니다.|  
|[How to: Group Related Constant Values Together](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-group-related-constant-values-together.md)|관련된 상수 값을 그룹화하는 방법을 보여 줍니다.|  
  
## 참조  
  
|||  
|-|-|  
|정의|용어|  
|[Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md)|[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서 미리 정의된 상수를 나열합니다.|  
|[Const Statement](../../../../visual-basic/language-reference/statements/const-statement.md)|`Const` 문 및 사용 방법에 대해 설명합니다.|  
|[Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)|`Option Strict` 문 및 사용 방법에 대해 설명합니다.|  
  
## 참고 항목  
 [Enumerations Overview](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)   
 [How to: Initialize an Array Variable in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)