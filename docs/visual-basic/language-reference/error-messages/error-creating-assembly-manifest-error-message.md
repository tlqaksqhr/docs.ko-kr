---
title: "Error creating assembly manifest: &lt;error message&gt; | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc30140"
  - "vbc30140"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30140"
ms.assetid: 1beb5aa0-7b79-4c85-946b-5c2d0a41d1d2
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# Error creating assembly manifest: &lt;error message&gt;
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 컴파일러가 어셈블리 링커\(Al.exe, Alink라고도 함\)를 호출하여 매니페스트를 사용해 어셈블리를 생성합니다.  링커가 어셈블리 만들기의 내보내기 전 단계에서 오류를 보고했습니다.  
  
 지정한 키 파일 또는 키 컨테이너에 문제가 있으면 이러한 현상이 발생할 수 있습니다.  어셈블리에 완전히 서명을 하려면 공개 키와 개인 키에 대한 정보가 포함된 유효한 키 파일을 제공해야 합니다.  어셈블리 서명을 연기하려면 **서명만 연기** 확인란을 선택하고 공개 키에 대한 정보가 포함된 유효한 키 파일을 제공해야 합니다.  어셈블리 서명을 연기할 때 개인 키는 필요하지 않습니다.  자세한 내용은 [How to: Sign an Assembly \(Visual Studio\)](http://msdn.microsoft.com/ko-kr/f468a7d3-234c-4353-924d-8e0ae5896564)을 참조하십시오.  
  
 **오류 ID:** BC30140  
  
### 이 오류를 해결하려면  
  
1.  따옴표로 묶인 오류 메시지를 파악한 다음 [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/ko-kr/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) 항목에서 오류 AL1019와 관련한 추가 설명과 권장 사항을 확인합니다.  
  
2.  오류가 계속 발생하면 해당 상황에 대한 정보를 수집하여 Microsoft 기술 지원 서비스에 알립니다.  
  
## 참고 항목  
 [How to: Sign an Assembly \(Visual Studio\)](http://msdn.microsoft.com/ko-kr/f468a7d3-234c-4353-924d-8e0ae5896564)   
 [프로젝트 디자이너, 서명 페이지](/visual-studio/ide/reference/signing-page-project-designer)   
 [Al.exe\(어셈블리 링커\)](../Topic/Al.exe%20\(Assembly%20Linker\).md)   
 [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/ko-kr/7f125d49-0a03-47a6-9ba9-d61a679a7d4b)   
 [의견 보내기](/visual-studio/ide/talk-to-us)