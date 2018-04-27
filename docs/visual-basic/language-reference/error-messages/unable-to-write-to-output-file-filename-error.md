---
title: '출력 파일에 쓸 수 없습니다 &#39; &lt;filename&gt;&#39;: &lt;오류&gt;'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31019
- bc31019
helpviewer_keywords:
- BC31019
ms.assetid: 0845b245-11bb-46fd-95ca-f6cef3c318ef
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a183f81a73c3c8034d9ba7366be8b36d425263da
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="unable-to-write-to-output-file-39ltfilenamegt39-lterrorgt"></a>출력 파일에 쓸 수 없습니다 &#39; &lt;filename&gt;&#39;: &lt;오류&gt;
파일을 만드는 동안 문제가 발생했습니다.  
  
 출력 파일을 쓰기 위해 열 수 없습니다. 파일 또는 파일이 포함된 폴더가 다른 프로세스에서 단독으로 사용되도록 열려 있거나 읽기 전용 특성이 설정되어 있을 수 있습니다.  
  
 파일이 단독으로 열리는 일반적인 상황은 다음과 같습니다.  
  
-   응용 프로그램이 이미 실행 중이며 해당 파일을 사용 중인 경우. 이 문제를 해결하려면 응용 프로그램이 실행되지 않고 있는지를 확인합니다.  
  
-   다른 응용 프로그램이 파일을 연 경우. 이 문제를 해결하려면 다른 응용 프로그램이 파일에 액세스하지 않고 있는지를 확인합니다. 파일에 액세스 중인 응용 프로그램이 확실하지 않은 경우도 있습니다. 이러한 경우 응용 프로그램을 종료하는 가장 쉬운 방법은 컴퓨터를 다시 시작하는 것입니다.  
  
 프로젝트 출력 파일 중 하나라도 읽기 전용으로 표시되어 있으면 이 예외가 throw됩니다.  
  
 **오류 ID:** BC31019  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  프로그램을 다시 컴파일하여 오류가 다시 발생하는지 확인합니다.  
  
2.  오류가 계속되면 작업을 저장하고 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]를 다시 시작합니다.  
  
3.  오류가 계속 발생하면 컴퓨터를 다시 시작합니다.  
  
4.  오류가 다시 발생 하는 경우에 Visual Basic을 다시 설치 하십시오.  
  
5.  다시 설치 후에도 오류가 계속 발생하면 Microsoft 기술 지원 서비스에 알립니다.  
  
### <a name="to-check-file-attributes-in-file-explorer"></a>파일 탐색기에서 파일 특성을 확인하려면  
  
1.  원하는 폴더를 엽니다.  
  
2.  클릭는 **뷰** 아이콘을 선택 하 고 **세부 정보**합니다.  
  
3.  열 머리글을 마우스 오른쪽 단추로 클릭 하 고 선택 **특성** 드롭 다운 목록에서 합니다.  
  
### <a name="to-change-the-attributes-of-a-file-or-folder"></a>파일이나 폴더의 특성을 변경하려면  
  
1.  **파일 탐색기**파일이 나 폴더를 마우스 오른쪽 단추로 클릭 하 고 선택 **속성**합니다.  
  
2.  에 **특성** 의 섹션은 **일반** 탭을 선택 취소는 **읽기 전용** 상자입니다.  
  
3.  Press **OK**.  
  
## <a name="see-also"></a>참고 항목  
 [의견 보내기](/visualstudio/ide/talk-to-us)
