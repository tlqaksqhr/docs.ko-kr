---
title: "Path/File access error | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbrID75"
dev_langs: 
  - "VB"
ms.assetid: 6ce3a161-7316-46bd-a785-0d50e5414020
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Path/File access error
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

파일 액세스 또는 디스크 액세스 작업을 수행하는 동안 운영 시스템에서 경로와 파일 이름을 연결하지 못했습니다.  
  
### 이 오류를 해결하려면  
  
1.  파일 사양의 형식이 올바로 지정되었는지 확인합니다.  파일 이름은 정규화된\(절대\) 경로 또는 상대 경로를 포함할 수 있습니다.  정규화된 경로는 다른 드라이브의 경로인 경우 드라이브 이름으로 시작하며 루트에서 파일까지의 명시적인 경로를 나열합니다.  정규화된 경로가 아닌 경로는 모두 현재 드라이브 및 디렉터리에 대한 상대 경로입니다.  
  
2.  기존의 읽기 전용 파일을 대체하는 파일을 저장하지 않도록 합니다.  이 경우 대상 파일의 읽기 전용 특성을 변경하거나 파일을 다른 이름으로 저장합니다.  
  
3.  읽기 전용 파일을 순차적`Output`또는 `Append` 모드에서 열지 않도록 합니다.  이 경우 파일을 `Input` 모드에서 열거나 파일의 읽기 전용 특성을 변경합니다.  
  
4.  데이터베이스 또는 문서 안에서 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 프로젝트를 변경하지 않도록 합니다.  
  
## 참고 항목  
 [Error Types](../../../visual-basic/programming-guide/language-features/error-types.md)