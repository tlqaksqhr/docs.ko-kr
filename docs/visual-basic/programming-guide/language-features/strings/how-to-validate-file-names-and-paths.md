---
title: "How to: Validate File Names and Paths in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - "file names, validating"
  - "strings [Visual Basic], validating"
  - "Boolean values"
  - "paths, validating"
ms.assetid: f673462d-57b7-4120-b13a-6a7592f7ab2c
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Validate File Names and Paths in Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

이 예제에서는 문자열이 파일 이름인지, 아니면 파일 경로인지를 나타내는 `Boolean` 값을 반환합니다.  유효성 검사를 통해 파일 시스템에서 허용하지 않는 문자가 이름에 포함되어 있는지 여부를 확인합니다.  
  
## 예제  
 [!code-vb[VbVbcnRegEx#4](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/how-to-validate-file-names-and-paths_1.vb)]  
  
 이 예제에서는 이름에서 콜론의 위치가 잘못되었는지, 이름이 없는 디렉터리인지 또는 이름의 길이가 시스템에서 정의한 최대 길이를 초과하는지 여부는 확인하지 않습니다.  또한 지정한 이름을 갖는 파일 시스템 리소스에 액세스할 권한이 응용 프로그램에 있는지 여부도 확인하지 않습니다.  
  
## 참고 항목  
 <xref:System.IO.Path.GetInvalidPathChars%2A>   
 [Validating Strings in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)