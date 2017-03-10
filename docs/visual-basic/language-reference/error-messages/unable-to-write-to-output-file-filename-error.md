---
title: "Unable to write to output file &#39;&lt;filename&gt;&#39;: &lt;error&gt; | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc31019"
  - "bc31019"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC31019"
ms.assetid: 0845b245-11bb-46fd-95ca-f6cef3c318ef
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# Unable to write to output file &#39;&lt;filename&gt;&#39;: &lt;error&gt;
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

파일을 만드는 동안 문제가 발생했습니다.  
  
 출력 파일을 쓰기 위해 열 수 없습니다.  파일 또는 파일이 포함된 폴더가 다른 프로세스에서 단독으로 사용되도록 열려 있거나 읽기 전용 특성이 설정되어 있을 수 있습니다.  
  
 파일이 단독으로 열리는 일반적인 상황은 다음과 같습니다.  
  
-   응용 프로그램이 이미 실행 중이며 해당 파일을 사용 중인 경우.  이 문제를 해결하려면 응용 프로그램이 실행되지 않고 있는지를 확인합니다.  
  
-   다른 응용 프로그램이 파일을 연 경우.  이 문제를 해결하려면 다른 응용 프로그램이 파일에 액세스하지 않고 있는지를 확인합니다.  파일에 액세스 중인 응용 프로그램이 확실하지 않은 경우도 있습니다. 이러한 경우 응용 프로그램을 종료하는 가장 쉬운 방법은 컴퓨터를 다시 시작하는 것입니다.  
  
 프로젝트 출력 파일 중 하나라도 읽기 전용으로 표시되어 있으면 이 예외가 throw됩니다.  
  
 **오류 ID:** BC31019  
  
### 이 오류를 해결하려면  
  
1.  프로그램을 다시 컴파일하여 오류가 다시 발생하는지 확인합니다.  
  
2.  오류가 계속되면 작업을 저장하고 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)]를 다시 시작합니다.  
  
3.  오류가 계속 발생하면 컴퓨터를 다시 시작합니다.  
  
4.  그래도 오류가 다시 발생하면 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]을 다시 설치합니다.  
  
5.  다시 설치 후에도 오류가 계속 발생하면 Microsoft 기술 지원 서비스에 알립니다.  
  
### 파일 탐색기에서 파일 특성을 확인하려면  
  
1.  원하는 폴더를 엽니다.  
  
2.  **보기** 아이콘을 클릭하고 **자세히**를 선택합니다.  
  
3.  열 머리글을 마우스 오른쪽 단추로 클릭하고 드롭다운 목록에서 **특성**을 선택합니다.  
  
### 파일이나 폴더의 특성을 변경하려면  
  
1.  **파일 탐색기**에서 파일이나 폴더를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.  
  
2.  **일반** 탭의 **특성** 섹션에서 **읽기 전용** 확인란의 선택을 취소합니다.  
  
3.  **확인**을 누릅니다.  
  
## 참고 항목  
 [의견 보내기](/visual-studio/ide/talk-to-us)