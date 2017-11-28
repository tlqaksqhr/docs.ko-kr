---
title: "방법: 명령줄 인수 표시(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: command-line arguments [C#], displaying
ms.assetid: b8479f2d-9e05-4d38-82da-2e61246e5437
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f6ae495eef227c6e4d9fb9ca0d4d0c031163fd52
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-command-line-arguments-c-programming-guide"></a>방법: 명령줄 인수 표시(C# 프로그래밍 가이드)
명령줄에서 실행 파일에 제공된 인수는 `Main`에 대한 선택적 매개 변수를 통해 액세스할 수 있습니다. 인수는 문자열 배열의 형태로 제공됩니다. 배열의 각 요소에는 하나의 인수가 포함되어 있습니다. 인수 사이의 공백은 제거됩니다. 예를 들어 명령줄에서 다음과 같이 가상 실행 파일을 호출한다고 가정합니다.  
  
|명령줄 입력|Main에 전달되는 문자열 배열|  
|----------------------------|-------------------------------------|  
|**executable.exe a b c**|"a"<br /><br /> "b"<br /><br /> "c"|  
|**executable.exe one two**|"one"<br /><br /> "two"|  
|**executable.exe "one two" three**|"one two"<br /><br /> "three"|  
  
> [!NOTE]
>  Visual Studio에서 응용 프로그램을 실행할 경우 [프로젝트 디자이너, 디버그 페이지](/visualstudio/ide/reference/debug-page-project-designer)에서 명령줄 인수를 지정할 수 있습니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 명령줄 응용 프로그램에 전달된 명령줄 인수를 표시합니다. 위의 표에서 첫 번째 항목에 대한 출력이 표시됩니다.  
  
 [!code-csharp[csProgGuideMain#9](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-display-command-line-arguments_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [csc.exe를 사용한 명령줄 빌드](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)  
 [Main()과 명령줄 인수](../../../csharp/programming-guide/main-and-command-args/index.md)  
 [방법: foreach를 사용하여 명령줄 인수 액세스](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)  
 [Main() 반환 값](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)
