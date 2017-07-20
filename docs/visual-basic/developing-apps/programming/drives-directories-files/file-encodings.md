---
title: "파일 인코딩(Visual Basic) | Microsoft Docs"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- character encodings
- files, encoding
- Unicode, file encoding
- file encoding
ms.assetid: ea2c5f5f-bbb1-4150-9928-b9951fa6bc57
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d59312951429780990e9cc048e3ad0671b81d8ae
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="file-encodings-visual-basic"></a>파일 인코딩(Visual Basic)
문자 인코딩이라고도 하는 파일 인코딩은 텍스트 처리 시 문자를 나타내는 방법을 지정합니다. 처리할 수 있거나 없는 언어 문자를 기준으로 특정 인코딩이 다른 인코딩보다 선호될 수 있지만, 일반적으로 유니코드가 선호됩니다.  
  
 파일을 읽거나 쓸 때 파일 인코딩을 잘못 일치시키면 예외 또는 잘못된 결과가 발생할 수 있습니다.  
  
## <a name="types-of-encodings"></a>인코딩 형식  
 파일 작업 시 기본 설정 인코딩은 유니코드입니다. 유니코드는 게시에 사용되는 전문 기호 및 특수 문자를 포함하여 첨단 컴퓨팅에서 사용되는 모든 문자를 16비트 코드 값으로 나타내는 전 세계 문자 인코딩 표준입니다.  
  
 이전 문자 인코딩 표준은 8비트 코드 값 또는 8비트 값의 조합을 사용하여 특정 언어나 지역에서 사용되는 문자를 나타내는 Windows ANSI 문자 집합 등의 기존 문자 집합으로 이루어져 있습니다.  
  
## <a name="encoding-class"></a>Encoding 클래스  
 <xref:System.Text.Encoding> 클래스는 문자 인코딩을 나타냅니다. 이 표에서는 사용 가능한 인코딩 형식을 나열하고 각 인코딩 형식을 설명합니다.  
  
|이름|설명|
|---|---|    
|<xref:System.Text.ASCIIEncoding>|유니코드 문자의 ASCII 문자 인코딩을 나타냅니다.|  
|<xref:System.Text.UnicodeEncoding>|유니코드 문자의 UTF-16 인코딩을 나타냅니다.|  
|<xref:System.Text.UTF32Encoding>|유니코드 문자의 UTF-32 인코딩을 나타냅니다.|  
|<xref:System.Text.UTF7Encoding>|유니코드 문자의 UTF-7 인코딩을 나타냅니다.|  
|<xref:System.Text.UTF8Encoding>|유니코드 문자의 UTF-8 인코딩을 나타냅니다.|  
  
## <a name="see-also"></a>참고 항목  
 [파일 읽기](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)   
 [파일에 쓰기](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)
