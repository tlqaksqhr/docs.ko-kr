---
title: "방법: Office 프로그래밍에 명명된 인수와 선택적 인수 사용(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- named and optional arguments [C#], Office programming
- optional arguments [C#], Office programming
- named arguments [C#], Office programming
ms.assetid: 65b8a222-bcd8-454c-845f-84adff5a356f
caps.latest.revision: "34"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: fc3c0f6910238ba20582280426b4a40e68b95dd8
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-use-named-and-optional-arguments-in-office-programming-c-programming-guide"></a>방법: Office 프로그래밍에 명명된 인수와 선택적 인수 사용(C# 프로그래밍 가이드)
[!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)]에서 도입된 명명된 인수 및 선택적 인수는 C# 프로그래밍의 편의성, 유연성 및 가독성을 향상합니다. 또한 이러한 기능은 Microsoft Office 자동화 API와 같은 COM 인터페이스에 대한 액세스에 큰 도움이 됩니다.  
  
 다음 예제의 [ConvertToTable](https://msdn.microsoft.com/library/bb216993.aspx) 메서드에는 열과 행 수, 서식, 테두리, 글꼴, 색 등의 테이블 특성을 나타내는 매개 변수 16개가 있습니다. 대부분의 경우 모든 매개 변수에 대해 특정 값을 지정하지는 않으므로 16개 매개 변수는 모두 선택 사항입니다. 그러나 명명된 인수와 선택적 인수를 사용하지 않을 경우 각 매개 변수에 대해 값 또는 자리 표시자 값을 제공해야 합니다. 명명된 인수와 선택적 인수를 사용할 경우 프로젝트에 필요한 매개 변수의 값만 지정합니다.  
  
 이 절차를 완료하려면 컴퓨터에 Microsoft Office Word가 설치되어 있어야 합니다.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-new-console-application"></a>새 콘솔 응용 프로그램을 만들려면  
  
1.  Visual Studio를 시작합니다.  
  
2.  **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.  
  
3.  **템플릿 범주** 창에서 **Visual C#**을 확장한 다음 **Windows**를 클릭합니다.  
  
4.  **템플릿** 창의 맨 위에서 **.NET Framework 4**가 **대상 프레임워크** 상자에 표시되는지 확인합니다.  
  
5.  **템플릿** 창에서 **콘솔 응용 프로그램**을 클릭합니다.  
  
6.  **이름** 필드에 프로젝트의 이름을 입력합니다.  
  
7.  **확인**을 클릭합니다.  
  
     **솔루션 탐색기**에 새 프로젝트가 표시됩니다.  
  
### <a name="to-add-a-reference"></a>참조를 추가하려면  
  
1.  **솔루션 탐색기**에서 프로젝트 이름을 마우스 오른쪽 단추로 클릭하고 **참조 추가**를 클릭합니다. **참조 추가** 대화 상자가 나타납니다.  
  
2.  **.NET** 페이지의 **구성 요소 이름** 목록에서 **Microsoft.Office.Interop.Word**를 선택합니다.  
  
3.  **확인**을 클릭합니다.  
  
### <a name="to-add-necessary-using-directives"></a>필요한 using 지시문을 추가하려면  
  
1.  **솔루션 탐색기**에서 **Program.cs** 파일을 마우스 오른쪽 단추로 클릭하고 **코드 보기**를 클릭합니다.  
  
2.  다음 `using` 지시문을 코드 파일의 맨 위에 추가합니다.  
  
     [!code-csharp[csProgGuideNamedAndOptional#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_1.cs)]  
  
### <a name="to-display-text-in-a-word-document"></a>Word 문서에 텍스트를 표시하려면  
  
1.  Program.cs의 `Program` 클래스에서 다음 메서드를 추가하여 Word 응용 프로그램과 Word 문서를 만듭니다. [Add](https://msdn.microsoft.com/library/microsoft.office.interop.word.documents.add.aspx) 메서드에는 선택적 매개 변수 4개가 있습니다. 이 예제에서는 해당 기본값을 사용합니다. 따라서 호출하는 문에 인수가 필요하지 않습니다.  
  
     [!code-csharp[csProgGuideNamedAndOptional#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_2.cs)]  
  
2.  메서드의 끝에 다음 코드를 추가하여 문서에서 텍스트를 표시할 위치 및 표시할 텍스트를 정의합니다.  
  
     [!code-csharp[csProgGuideNamedAndOptional#7](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_3.cs)]  
  
### <a name="to-run-the-application"></a>응용 프로그램을 실행하려면  
  
1.  다음 문을 Main에 추가합니다.  
  
     [!code-csharp[csProgGuideNamedAndOptional#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_4.cs)]  
  
2.  Ctrl+F5를 눌러 프로젝트를 실행합니다. 지정된 텍스트를 포함하는 Word 문서가 나타납니다.  
  
### <a name="to-change-the-text-to-a-table"></a>텍스트를 표로 변경하려면  
  
1.  `ConvertToTable` 메서드를 사용하여 텍스트를 표로 묶습니다. 이 메서드에는 선택적 매개 변수 16개가 있습니다. IntelliSense는 다음 그림과 같이 선택적 매개 변수를 중괄호로 묶습니다.  
  
     ![ConvertToTable 메서드의 매개 변수 목록](../../../csharp/programming-guide/classes-and-structs/media/convert_tableparameters.png "Convert_TableParameters")  
ConvertToTable 매개 변수  
  
     명명된 인수 및 선택적 인수를 사용하면 변경하려는 매개 변수의 값만 지정할 수 있습니다. `DisplayInWord` 메서드의 끝에 다음 코드를 추가하여 간단한 표를 만듭니다. 인수는 `range`의 텍스트 문자열에 있는 쉼표가 표의 셀을 구분하도록 지정합니다.  
  
     [!code-csharp[csProgGuideNamedAndOptional#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_5.cs)]  
  
     이전 버전의 C#에서 `ConvertToTable`을 호출하려면 다음 코드와 같이 각 매개 변수에 대한 참조 인수가 필요합니다.  
  
     [!code-csharp[csProgGuideNamedAndOptional#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_6.cs)]  
  
2.  Ctrl+F5를 눌러 프로젝트를 실행합니다.  
  
### <a name="to-experiment-with-other-parameters"></a>다른 매개 변수로 실험하려면  
  
1.  열 1개와 행 3개가 포함되도록 표를 변경하려면 `DisplayInWord`의 마지막 줄을 다음 문으로 바꾼 다음 Ctrl+F5를 입력합니다.  
  
     [!code-csharp[csProgGuideNamedAndOptional#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_7.cs)]  
  
2.  미리 정의된 표 형식을 지정하려면 `DisplayInWord`의 마지막 줄을 다음 문으로 바꾼 다음 Ctrl+F5를 입력합니다. 형식은 [WdTableFormat](https://msdn.microsoft.com/library/microsoft.office.interop.word.wdtableformat.aspx) 상수 중 하나일 수 있습니다.  
  
     [!code-csharp[csProgGuideNamedAndOptional#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_8.cs)]  
  
## <a name="example"></a>예  
 다음 코드에는 전체 예제가 포함되어 있습니다.  
  
 [!code-csharp[csProgGuideNamedAndOptional#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-named-and-optional-arguments-in-office-programming_9.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [명명된 인수 및 선택적 인수](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)
