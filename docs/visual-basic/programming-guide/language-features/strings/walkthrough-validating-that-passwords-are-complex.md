---
title: "Walkthrough: Validating That Passwords Are Complex (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "String data type, validation"
ms.assetid: 5d9a918f-6c1f-41a3-a019-b5c2b8ce0381
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Walkthrough: Validating That Passwords Are Complex (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

이 메서드는 강력한 암호 특성을 검사하고 암호가 실패하는지 검사하는 정보로 문자열 매개 변수를 업데이트합니다.  
  
 암호는 사용자 인증을 위해 보안 시스템에서 사용될 수 있는데  이때 인증되지 않은 사용자가 추측하기 어려운 암호를 사용해야 합니다.  공격자는 *사전 공격* 프로그램을 사용하여 일반 사전이나 다양한 언어로 되어 있는 여러 사전에 있는 모든 단어를 반복하면서 어떤 단어가 사용자 암호로 사용되는지 테스트할 수 있습니다.  "Yankees" 또는 "Mustang"과 같이 강력하지 않은 암호는 빨리 추측될 수 있습니다.  "?You'L1N3vaFiNdMeyeP@sSWerd\!"와 같은 강력한 암호는 훨씬 추측하기 어렵습니다.  암호 보호 시스템은 사용자가 강력한 암호를 선택했는지 확인해야 합니다.  
  
 강력한 암호는 대문자, 소문자, 숫자 그리고 특수 문자가 혼합된 복합어이며 한 단어가 아닙니다.  이 예제는 복합성을 확인하는 방법을 보여 줍니다.  
  
## 예제  
  
### 코드  
 [!code-vb[VbVbcnRegEx#1](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/visualbasic/walkthrough-validating-t_1.vb)]  
  
## 코드 컴파일  
 해당 암호를 포함하는 문자열을 전달하여 이 메서드를 호출합니다.  
  
 이 예제에는 다음 사항이 필요합니다.  
  
-   <xref:System.Text.RegularExpressions> 네임스페이스의 멤버에 대한 액세스 권한.  코드에서 멤버 이름을 정규화하지 않는 경우에는 `Imports` 문을 추가합니다.  자세한 내용은 [Imports Statement \(.NET Namespace and Type\)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)을 참조하십시오.  
  
## 보안  
 네트워크를 통해 암호를 이동하는 경우 데이터 전송에 안전한 방법을 사용해야 합니다.  자세한 내용은 [ASP.NET Web Application Security](../Topic/ASP.NET%20Web%20Application%20Security.md)을 참조하십시오.  
  
 다음과 같이 추가 복합성 검사를 추가해서 `ValidatePassword` 함수의 정확성을 향상시킬 수 있습니다.  
  
-   사용자 이름, 사용자 ID 및 응용 프로그램 정의 사전과 암호 및 해당 부분 문자열을 비교합니다.  또한 비교를 수행할 때 시각적으로 비슷한 문자를 동일한 것으로 취급합니다.  예를 들어, 문자 "l" 및 "e"를 숫자 "1" 및 "3"과 동일하게 취급합니다.  
  
-   대문자가 하나만 있는 경우 암호의 첫 문자가 아니어야 합니다.  
  
-   암호의 마지막 두 자는 문자여야 합니다.  
  
-   암호의 모든 기호를 키보드의 상위 행에서 입력하지 않아야 합니다.  
  
## 참고 항목  
 <xref:System.Text.RegularExpressions.Regex>   
 [ASP.NET Web Application Security](../Topic/ASP.NET%20Web%20Application%20Security.md)