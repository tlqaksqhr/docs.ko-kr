---
title: "/filealign | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "sections compiler option [Visual Basic]"
  - "alignment compiler option [Visual Basic]"
  - "-filealign compiler option [Visual Basic]"
  - "section alignment"
  - "/filealign compiler option [Visual Basic]"
  - "filealign compiler option [Visual Basic]"
ms.assetid: cc61ec3d-ad38-4b28-9659-099d73cad099
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# /filealign
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

출력 파일의 섹션을 맞출 위치를 지정합니다.  
  
## 구문  
  
```  
/filealign:number  
```  
  
## 인수  
 `number`  
 필수 요소.  출력 파일의 섹션 맞춤을 지정하는 값으로,  유효한 값은 512, 1024, 2048, 4096 및 8192입니다.  이 값은 바이트 단위입니다.  
  
## 설명  
 `/filealign` 옵션을 사용하면 출력 파일의 섹션 맞춤을 지정할 수 있습니다.  섹션은 코드나 데이터가 포함된 PE 파일의 연속된 메모리 블록입니다.  `/filealign` 옵션을 사용하면 비표준 맞춤으로 응용 프로그램을 컴파일할 수 있습니다. 대부분의 개발자는 이 옵션을 사용할 필요가 없습니다.  
  
 각 섹션은 `/filealign` 값의 배수인 경계에 맞춰지고  고정된 기본값은 없습니다.  `/filealign`을 지정하지 않으면 컴파일러가 컴파일 타임에 기본값을 선택합니다.  
  
 섹션 크기를 지정하여 출력 파일의 크기를 변경할 수 있습니다.  소형 장치에서 실행되는 프로그램의 경우 섹션 크기 수정 기능이 유용하게 사용될 수 있습니다.  
  
> [!NOTE]
>  `/filealign` 옵션은 Visual Studio 개발 환경에서는 사용할 수 없고 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.  
  
## 참고 항목  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)