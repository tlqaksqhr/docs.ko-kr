---
title: "File Encodings (Visual Basic) | Microsoft Docs"
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
  - "character encodings"
  - "files, encoding"
  - "Unicode, file encoding"
  - "file encoding"
ms.assetid: ea2c5f5f-bbb1-4150-9928-b9951fa6bc57
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# File Encodings (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

문자 인코딩이라고도 하는 파일 인코딩은 텍스트를 처리할 때 문자를 나타낼 방식을 지정합니다.  일반적으로 유니코드가 사용되지만 해당 인코딩이 처리할 수 있는 언어 문자에 따라 주로 사용되는 인코딩이 있습니다.  
  
 파일을 읽거나 쓸 때 파일 인코딩이 제대로 일치하지 않으면 예외나 올바르지 않은 결과가 발생할 수 있습니다.  
  
## 인코딩 형식  
 유니코드는 파일로 작업할 때 많이 사용하는 인코딩입니다.  유니코드는 기술 기호 및 출판에 사용되는 특수 문자를 포함하여 현재 컴퓨팅에서 사용되는 모든 문자를 16비트 코드 값을 사용하여 나타내는 국제 문자 인코딩 표준입니다.  
  
 이전 문자 인코딩 표준은 8비트 코드 값을 사용하는 Windows ANSI 문자 집합이나 8비트 값의 조합 등과 같은 기존 문자 집합으로 구성되어 특정 언어나 지역에 사용되는 문자를 나타냈습니다.  
  
## Encoding 클래스  
 <xref:System.Text.Encoding> 클래스는 문자 인코딩을 나타냅니다.  이 표에서는 사용 가능한 인코딩 형식을 나열하고 각각에 대해 설명합니다.  
  
|||  
|-|-|  
|Name|설명|  
|<xref:System.Text.ASCIIEncoding>|유니코드 문자의 ASCII 문자 인코딩을 나타냅니다.|  
|<xref:System.Text.UnicodeEncoding>|유니코드 문자의 UTF\-16 인코딩을 나타냅니다.|  
|<xref:System.Text.UTF32Encoding>|유니코드 문자의 UTF\-32 인코딩을 나타냅니다.|  
|<xref:System.Text.UTF7Encoding>|유니코드 문자의 UTF\-7 인코딩을 나타냅니다.|  
|<xref:System.Text.UTF8Encoding>|유니코드 문자의 UTF\-8 인코딩을 나타냅니다.|  
  
## 참고 항목  
 [Reading from Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)   
 [Writing to Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)