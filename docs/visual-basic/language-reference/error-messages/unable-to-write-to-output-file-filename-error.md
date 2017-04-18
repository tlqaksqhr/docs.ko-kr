---
title: "출력 파일에 쓸 수 없습니다. &quot;&lt;filename&gt;&quot;: &lt;오류&gt; | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31019
- bc31019
dev_langs:
- VB
helpviewer_keywords:
- BC31019
ms.assetid: 0845b245-11bb-46fd-95ca-f6cef3c318ef
caps.latest.revision: 10
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: fe093ec3b36ba733cb9b0c162e242c8dce6b7c78
ms.lasthandoff: 03/13/2017

---
# <a name="unable-to-write-to-output-file-39ltfilenamegt39-lterrorgt"></a>출력 파일에 쓸 수 없습니다. '&lt;filename&gt;': &lt;오류&gt;
파일을 만드는 동안 문제가 발생했습니다.  
  
 출력 파일을 쓰기 위해 열 수 없습니다. 파일 또는 파일이 포함된 폴더가 다른 프로세스에서 단독으로 사용되도록 열려 있거나 읽기 전용 특성이 설정되어 있을 수 있습니다.  
  
 파일이 단독으로 열리는 일반적인 상황은 다음과 같습니다.  
  
-   응용 프로그램이 이미 실행 중이며 해당 파일을 사용 중인 경우. 이 문제를 해결하려면 응용 프로그램이 실행되지 않고 있는지를 확인합니다.  
  
-   다른 응용 프로그램이 파일을 연 경우. 이 문제를 해결하려면 다른 응용 프로그램이 파일에 액세스하지 않고 있는지를 확인합니다. 파일에 액세스 중인 응용 프로그램이 확실하지 않은 경우도 있습니다. 이러한 경우 응용 프로그램을 종료하는 가장 쉬운 방법은 컴퓨터를 다시 시작하는 것입니다.  
  
 프로젝트 출력 파일 중 하나라도 읽기 전용으로 표시되어 있으면 이 예외가 throw됩니다.  
  
 **오류 ID:** BC31019  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  프로그램을 다시 컴파일하여 오류가 다시 발생하는지 확인합니다.  
  
2.  오류가 계속되면 작업을 저장하고 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]를 다시 시작합니다.  
  
3.  오류가 계속 발생하면 컴퓨터를 다시 시작합니다.  
  
4.  그래도 오류가 다시 발생하면 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]을 다시 설치합니다.  
  
5.  다시 설치 후에도 오류가 계속 발생하면 Microsoft 기술 지원 서비스에 알립니다.  
  
### <a name="to-check-file-attributes-in-file-explorer"></a>파일 탐색기에서 파일 특성을 확인하려면  
  
1.  원하는 폴더를 엽니다.  
  
2.  클릭 된 **보기** 아이콘 선택 **세부 정보**합니다.  
  
3.  열 머리글을 마우스 오른쪽 단추로 클릭 하 고 선택 **특성** 드롭 다운 목록에서 합니다.  
  
### <a name="to-change-the-attributes-of-a-file-or-folder"></a>파일이나 폴더의 특성을 변경하려면  
  
1.  **파일 탐색기**파일 또는 폴더를 마우스 오른쪽 단추로 클릭 하 고 선택 **속성**합니다.  
  
2.  에 **특성** 의 섹션은 **일반** 탭을 선택 취소는 **읽기 전용** 상자입니다.  
  
3.  Press **OK**.  
  
## <a name="see-also"></a>참고 항목  
 [의견 보내기](https://docs.microsoft.com/visualstudio/ide/talk-to-us)
