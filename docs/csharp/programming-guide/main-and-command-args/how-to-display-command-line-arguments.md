---
title: "방법: 명령줄 인수 표시(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "명령줄 인수[C#], 표시"
ms.assetid: b8479f2d-9e05-4d38-82da-2e61246e5437
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# 방법: 명령줄 인수 표시(C# 프로그래밍 가이드)
명령줄에서 실행 파일에 제공되는 인수에는 `Main`의 선택적 매개 변수를 통해 액세스할 수 있습니다.  인수는 문자열의 배열 형식으로 제공됩니다.  배열의 각 요소에는 인수 하나가 포함됩니다.  인수 사이의 공백은 제거됩니다.  예를 들어, 가상의 실행 파일에 대한 다음과 같은 명령줄 호출을 생각해 볼 수 있습니다.  
  
|명령줄 입력|Main에 전달되는 문자열 배열|  
|------------|-----------------------|  
|**executable.exe a b c**|"a"<br /><br /> "b"<br /><br /> "c"|  
|**executable.exe one two**|"one"<br /><br /> "two"|  
|**executable.exe "one two" three**|"one two"<br /><br /> "three"|  
  
> [!NOTE]
>  Visual Studio에서 응용 프로그램을 실행할 때 [프로젝트 디자이너, 디버그 페이지](/visual-studio/ide/reference/debug-page-project-designer)에서 명령줄 인수를 지정할 수 있습니다.  
  
## 예제  
 이 예제에서는 명령줄 응용 프로그램에 전달되는 명령줄 인수를 표시합니다.  위 표의 첫 번째 항목에 대한 출력이 표시됩니다.  
  
 [!code-cs[csProgGuideMain#9](../../../csharp/programming-guide/inside-a-program/codesnippet/csharp/how-to-display-command-l_1.cs)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [Command\-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)   
 [Main\(\)과 명령줄 인수](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md)   
 [방법: foreach를 사용하여 명령줄 인수 액세스](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)   
 [Main\(\) 반환 값](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)