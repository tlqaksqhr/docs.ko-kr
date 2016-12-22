---
title: "연습: Office 프로그래밍(C# 및 Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Office 프로그래밍[C#]"
  - "Office 프로그래밍[Visual Basic]"
  - "Office, Visual Basic 및 C#에서 프로그래밍"
ms.assetid: 519cff31-f80b-4f0e-a56b-26358d0f8c51
caps.latest.revision: 46
caps.handback.revision: 46
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 연습: Office 프로그래밍(C# 및 Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

[!INCLUDE[vs_dev10_long](../../../csharp/programming-guide/interop/includes/vs_dev10_long_md.md)]에는 Microsoft Office 프로그래밍을 개선하는 새로운 기능이 C\# 및 Visual Basic에 도입되었습니다.  각 언어에는 다른 언어에 이미 포함되어 있었던 기능이 추가되었습니다.  
  
 C\#의 새로운 기능으로는 명명된 인수\/선택적 인수, `dynamic` 형식의 반환 값, 그리고 COM 프로그래밍에서 `ref` 키워드를 생략하고 인덱싱된 속성에 액세스하는 기능이 있습니다.  Visual Basic 새로운 기능으로는 자동 구현 속성, 람다 식의 문, 컬렉션 이니셜라이저 등이 있습니다.  
  
 이 두 언어에서는 PIA\(주 Interop 어셈블리\)를 사용자 컴퓨터에 배포하지 않아도 COM 구성 요소와 상호 작용하는 어셈블리를 배포할 수 있도록 하는 형식 정보를 포함할 수 있습니다.  자세한 내용은 [연습: 관리되는 어셈블리의 형식 포함](../Topic/Walkthrough:%20Embedding%20Types%20from%20Managed%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)을 참조하세요.  
  
 이 연습에서는 Office 프로그래밍과 관련된 새로운 기능을 설명하지만 이러한 기능은 대부분 일반 프로그래밍에서도 유용합니다.  연습에서는 먼저 Excel 추가 기능 응용 프로그램을 사용하여 Excel 통합 문서를 만듭니다.  그런 다음 통합 문서 링크를 포함하는 Word 문서를 만듭니다.  마지막으로 PIA 종속성을 설정 및 해제하는 방법에 대해 알아봅니다.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 Microsoft Office Excel 2013 또는 2007 이상 버전과 Microsoft Office Word 2013 또는 2007 이상 버전이 컴퓨터에 설치되어 있어야 합니다.  
  
 [!INCLUDE[windowsver](../../../csharp/programming-guide/interop/includes/windowsver_md.md)] 이전 버전의 운영 체제를 사용 중이라면 [!INCLUDE[dnprdnlong](../../../csharp/programming-guide/events/includes/dnprdnlong_md.md)]이 설치되어 있는지 확인합니다.  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### Excel 추가 기능 응용 프로그램을 설치하려면  
  
1.  Visual Studio를 시작합니다.  
  
2.  **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.  
  
3.  **설치된 템플릿** 창에서 **Visual Basic** 또는 **Visual C\#**을 확장하고 **Office**를 확장한 다음 **2013** 또는 **2010**이나 **2007**을 클릭합니다.  
  
4.  **템플릿** 창에서 **Excel 2013 추가 기능** 또는 **Excel 2010 추가 기능**이나 **Excel 2007 추가 기능**을 클릭합니다.  
  
5.  **템플릿** 창 위쪽의 **대상 프레임워크** 상자에 **.NET Framework 4** 이상 버전이 표시되어 있는지 확인합니다.  
  
6.  원하는 경우 **이름** 상자에 프로젝트의 이름을 입력합니다.  
  
7.  **확인**을 클릭합니다.  
  
8.  **솔루션 탐색기**에 새 프로젝트가 표시됩니다.  
  
### 참조를 추가하려면  
  
1.  **솔루션 탐색기**에서 프로젝트 이름을 마우스 오른쪽 단추로 클릭하고 **참조 추가**를 클릭합니다.  **참조 추가** 대화 상자가 나타납니다.  
  
2.  **어셈블리** 탭에서 **Microsoft.Office.Interop.Excel** 버전 15.0.0.0 또는 14.0.0.0\(Excel 2010\)이나 12.0.0.0\(Excel 2007\)을 선택하고 **구성 요소 이름** 목록에서 Ctrl 키를 누른 상태로 **Microsoft.Office.Interop.Word** 버전 15.0.0.0 또는 버전 14.0.0.0\(Word 2010\)이나 12.0.0.0\(Word 2007\)을 선택합니다.  이러한 어셈블리가 보이지 않으면 어셈블리가 설치되어 있으며 표시되는지를 확인해야 할 수 있습니다\([방법: Office 주 Interop 어셈블리 설치](../Topic/How%20to:%20Install%20Office%20Primary%20Interop%20Assemblies.md) 참조\).  
  
3.  **확인**을 클릭합니다.  
  
### 필요한 Import 문 또는 using 문을 추가하려면  
  
1.  **솔루션 탐색기**에서 **ThisAddIn.vb** 또는 **ThisAddIn.cs** 파일을 마우스 오른쪽 단추로 클릭한 다음 **코드 보기**를 클릭합니다.  
  
2.  다음 `Imports` 문\(Visual Basic\) 또는 `using` 지시문\(C\#\)이 없으면 코드 파일 맨 위에 추가합니다.  
  
     [!code-cs[csOfficeWalkthrough#1](../../../csharp/programming-guide/interop/codesnippet/CSharp/walkthrough-office-programming_1.cs)]
     [!code-vb[csOfficeWalkthrough#1](../../../csharp/programming-guide/interop/codesnippet/VisualBasic/walkthrough-office-programming_1.vb)]  
  
### 은행 계좌 목록을 만들려면  
  
1.  **솔루션 탐색기**에서 프로젝트 이름을 마우스 오른쪽 단추로 클릭하고 **추가**를 클릭한 다음 **클래스**를 클릭합니다.  Visual Basic을 사용하는 경우 Account.vb로, C\#을 사용하는 경우에는 Account.cs로 클래스의 이름을 지정합니다.  **추가**를 클릭합니다.  
  
2.  `Account` 클래스 정의를 다음 코드로 바꿉니다.  클래스 정의는 Visual Studio 2010의 Visual Basic에서 새롭게 제공되는 *자동 구현 속성*을 사용합니다.  자세한 내용은 [Auto\-Implemented Properties](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md)을 참조하세요.  
  
     [!code-cs[csOfficeWalkthrough#2](../../../csharp/programming-guide/interop/codesnippet/CSharp/walkthrough-office-programming_2.cs)]
     [!code-vb[csOfficeWalkthrough#2](../../../csharp/programming-guide/interop/codesnippet/VisualBasic/walkthrough-office-programming_2.vb)]  
  
3.  계좌 2개가 포함된 `bankAccounts` 목록을 만들려면 ThisAddIn.vb 또는 ThisAddIn.cs의 `ThisAddIn_Startup` 메서드에 다음 코드를 추가합니다.  목록 선언은 Visual Studio 2010의 Visual Basic에서 새롭게 제공되는 *컬렉션 이니셜라이저*를 사용합니다.  자세한 내용은 [Collection Initializers](../../../visual-basic/reference/command-line-compiler/index.md)을 참조하세요.  
  
     [!code-cs[csOfficeWalkthrough#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/walkthrough-office-programming_3.cs)]
     [!code-vb[csOfficeWalkthrough#3](../../../csharp/programming-guide/interop/codesnippet/VisualBasic/walkthrough-office-programming_3.vb)]  
  
### 데이터를 Excel로 내보내려면  
  
1.  같은 파일에서 `ThisAddIn` 클래스에 다음 메서드를 추가합니다.  이 메서드는 Excel 통합 문서를 설정하고 데이터를 해당 통합 문서로 내보냅니다.  
  
     [!code-cs[csOfficeWalkthrough#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/walkthrough-office-programming_4.cs)]
     [!code-vb[csOfficeWalkthrough#4](../../../csharp/programming-guide/interop/codesnippet/VisualBasic/walkthrough-office-programming_4.vb)]  
  
     이 메서드에는 두 가지 새로운 C\# 기능이 사용됩니다.  Visual Basic에서는 이 두 기능이 모두 이미 포함되어 있습니다.  
  
    -   [Add](http://go.microsoft.com/fwlink/?LinkId=210910) 메서드에는 특정 템플릿을 지정하기 위한 *선택적 매개 변수*가 있습니다.  [!INCLUDE[csharp_dev10_long](../../../csharp/programming-guide/classes-and-structs/includes/csharp_dev10_long_md.md)]에서 새롭게 제공되는 선택적 매개 변수를 사용하면 매개 변수의 기본값을 사용하려는 경우 해당 매개 변수의 인수를 생략할 수 있습니다.  앞의 예제에서는 인수가 전송되지 않으므로 `Add`는 기본 템플릿을 사용하며 새 통합 문서를 만듭니다.  이전 버전의 C\#에서 이와 동일한 문을 사용하려면 자리 표시자 인수인 `excelApp.Workbooks.Add(Type.Missing)`를 사용해야 했습니다.  
  
         자세한 내용은 [명명된 인수 및 선택적 인수](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)을 참조하세요.  
  
    -   [Range](http://go.microsoft.com/fwlink/?LinkId=210911) 개체의 `Range` 및 `Offset` 속성은 *인덱싱된 속성* 기능을 사용합니다.  이 기능을 사용하면 다음과 같은 일반적인 C\# 구문을 통해 COM 형식에서 이러한 속성을 사용할 수 있습니다.  또한 인덱싱된 속성에서는 `Range` 개체의 `Value` 속성을 사용할 수 있으므로 `Value2` 속성을 사용할 필요가 없습니다.  `Value` 속성은 인덱싱된 속성이지만 인덱스는 선택 사항입니다.  다음 예제에서는 선택적 인수와 인덱싱된 속성이 함께 사용됩니다.  
  
         [!code-cs[csOfficeWalkthrough#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/walkthrough-office-programming_5.cs)]  
  
         이전 버전의 언어에서는 다음과 같은 특수 구문을 사용해야 했습니다.  
  
         [!code-cs[csOfficeWalkthrough#6](../../../csharp/programming-guide/interop/codesnippet/CSharp/walkthrough-office-programming_6.cs)]  
  
         인덱싱된 속성을 직접 만들 수는 없습니다.  이 기능은 기존 인덱싱된 속성의 사용만을 지원합니다.  
  
         자세한 내용은 [방법: COM Interop 프로그래밍에서 인덱싱된 속성 사용](../../../csharp/programming-guide/interop/how-to-use-indexed-properties-in-com-interop-rogramming.md)을 참조하세요.  
  
2.  열 너비를 콘텐츠에 맞게 조정하려면 `DisplayInExcel` 끝에 다음 코드를 추가합니다.  
  
     [!code-cs[csOfficeWalkthrough#7](../../../csharp/programming-guide/interop/codesnippet/CSharp/walkthrough-office-programming_7.cs)]
     [!code-vb[csOfficeWalkthrough#7](../../../csharp/programming-guide/interop/codesnippet/VisualBasic/walkthrough-office-programming_7.vb)]  
  
     여기서 추가하는 코드는 C\# 2010의 또 다른 새 기능, 즉 Office 등의 COM 호스트에서 반환되는 `Object` 값을 [dynamic](../../../csharp/language-reference/keywords/dynamic.md) 형식인 것처럼 처리하는 기능을 보여 줍니다.  [\/link](../../../csharp/language-reference/compiler-options/link-compiler-option.md) 컴파일러 옵션을 통해 어셈블리를 참조할 때 **Interop 형식 포함**을 기본값인 `True` 또는 그와 동일한 값으로 설정하면 이 작업이 자동으로 수행됩니다.  `dynamic` 형식을 사용하면 Visual Basic의 기존 기능인 런타임에 바인딩을 사용할 수 있으며, Visual C\# 2008 이하 버전 언어에서 필요했던 명시적 캐스팅을 사용할 필요가 없습니다.  
  
     예를 들어 `excelApp.Columns[1]`은 `Object`를 반환하며 `AutoFit`은 Excel [Range](http://go.microsoft.com/fwlink/?LinkId=210911) 메서드입니다.  `dynamic`을 사용하지 않는 경우에는 `AutoFit` 메서드를 호출하기 전에 `excelApp.Columns[1]`에서 반환하는 개체를 `Range` 인스턴스로 캐스팅해야 합니다.  
  
     [!code-cs[csOfficeWalkthrough#8](../../../csharp/programming-guide/interop/codesnippet/CSharp/walkthrough-office-programming_8.cs)]  
  
     Interop 형식 포함에 대한 자세한 내용은 이 항목 뒷부분의 "PIA 참조를 찾으려면" 및 "PIA 종속성을 복원하려면" 절차를 참조하세요.  `dynamic`에 대한 자세한 내용은 [동적](../../../csharp/language-reference/keywords/dynamic.md) 또는 [유형 동적 사용](../../../csharp/programming-guide/types/using-type-dynamic.md)을 참조하세요.  
  
### DisplayInExcel를 호출하려면  
  
1.  `ThisAddIn_StartUp` 메서드의 끝에 다음 코드를 추가합니다.  `DisplayInExcel` 호출에는 두 개의 인수가 포함됩니다.  첫 번째 인수는 처리할 계좌 목록의 이름이고,  두 번째 인수는 데이터 처리 방법을 정의하는 여러 줄 람다 식입니다.  각 계좌의 `ID` 및 `balance` 값은 인접 셀에 표시되며 잔액이 0보다 작으면 행은 빨간색으로 표시됩니다.  여러 줄 람다 식은 Visual Basic 2010의 새로운 기능입니다.  자세한 내용은 [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)을 참조하세요.  
  
     [!code-cs[csOfficeWalkthrough#9](../../../csharp/programming-guide/interop/codesnippet/CSharp/walkthrough-office-programming_9.cs)]
     [!code-vb[csOfficeWalkthrough#9](../../../csharp/programming-guide/interop/codesnippet/VisualBasic/walkthrough-office-programming_9.vb)]  
  
2.  F5 키를 눌러 프로그램을 실행합니다.  그러면 계좌의 데이터가 포함된 Excel 워크시트가 표시됩니다.  
  
### Word 문서를 추가하려면  
  
1.  `ThisAddIn_StartUp` 메서드 끝에 다음 코드를 추가하여 Excel 통합 문서에 대한 링크가 포함된 Word 문서를 만듭니다.  
  
     [!code-cs[csOfficeWalkthrough#10](../../../csharp/programming-guide/interop/codesnippet/CSharp/walkthrough-office-programming_10.cs)]
     [!code-vb[csOfficeWalkthrough#10](../../../csharp/programming-guide/interop/codesnippet/VisualBasic/walkthrough-office-programming_10.vb)]  
  
     이 코드는 COM 프로그래밍에서 `ref` 키워드를 생략하는 기능, 명명된 인수, 선택적 인수 등 다양한 C\#의 새로운 기능을 보여 줍니다.  Visual Basic에는 이러한 기능이 이미 포함되어 있습니다.  [PasteSpecial](http://go.microsoft.com/fwlink/?LinkId=147099) 메서드에는 모두 선택적 참조 매개 변수로 정의되는 7개 매개 변수가 있습니다.  Visual C\# 2010 이전 버전에서는 전송할 의미 있는 값이 없더라도 7개 매개 변수에 대해 인수로 사용할 개체 변수를 정의해야 했습니다.  명명된 인수와 선택적 인수를 사용하면 액세스할 매개 변수를 이름으로 지정하고 해당 매개 변수에만 인수를 보낼 수 있습니다.  이 예제에서는 클립보드에 통합 문서 링크를 만들어야 하고\(`Link` 매개 변수\) Word 문서에 링크를 아이콘으로 표시하도록\(`DisplayAsIcon` 매개 변수\) 지정하는 인수를 전송합니다.  Visual C\# 2010에서는 이러한 인수의 `ref` 키워드를 생략할 수도 있습니다.  Visual C\# 2008의 다음 코드 세그먼트를 Visual C\# 2010에서는 맨 아래의 코드 줄 하나로 대체할 수 있습니다.  
  
     [!code-cs[csOfficeWalkthrough#11](../../../csharp/programming-guide/interop/codesnippet/CSharp/walkthrough-office-programming_11.cs)]  
  
### 응용 프로그램을 실행하려면  
  
1.  F5 키를 눌러 응용 프로그램을 실행합니다.  Excel이 시작되고 `bankAccounts`의 두 계좌 정보가 포함된 표가 표시됩니다.  그런 후에 Excel 표의 링크가 포함된 Word 문서가 표시됩니다.  
  
### 완료된 프로젝트를 정리하려면  
  
1.  Visual Studio의 **빌드** 메뉴에서 **솔루션 정리**를 클릭합니다.  이렇게 하지 않으면 컴퓨터에서 Excel을 열 때마다 추가 기능이 실행됩니다.  
  
### PIA 참조를 찾으려면  
  
1.  응용 프로그램을 다시 실행하되 **솔루션 정리**를 클릭하지는 않습니다.  
  
2.  **시작** 메뉴에서 **모든 프로그램**을 클릭합니다.  그런 다음 **Microsoft Visual Studio 2013**, **Visual Studio 도구**, **Visual Studio 명령 프롬프트\(2013\)**를 차례로 클릭합니다.  
  
3.  Visual Studio 명령 프롬프트\(2013\) 창에 `ildasm`을 입력하고 Enter 키를 누릅니다.  IL DASM 창이 나타납니다.  
  
4.  IL DASM 창의 **파일** 메뉴에서 **열기**를 클릭합니다.  **Visual Studio 2013**과 **프로젝트**를 차례로 두 번 클릭합니다.  프로젝트 폴더를 열고 *프로젝트 이름*.dll에서 bin\/Debug 폴더를 확인한 후  *프로젝트 이름*.dll을 두 번 클릭합니다.  새 창에 프로젝트 특성과 기타 모듈 및 어셈블리에 대한 참조가 표시됩니다.  어셈블리에는 `Microsoft.Office.Interop.Excel` 및 `Microsoft.Office.Interop.Word` 네임스페이스가 포함되어 있습니다.  기본적으로 Visual Studio 2013에서는 컴파일러가 참조되는 PIA에서 필요한 형식을 어셈블리로 가져옵니다.  
  
     자세한 내용은 [방법: 어셈블리 내용 보기](../Topic/How%20to:%20View%20Assembly%20Contents.md)을 참조하세요.  
  
5.  **MANIFEST** 아이콘을 두 번 클릭합니다.  프로젝트가 참조하는 항목이 들어 있는 어셈블리 목록이 포함된 창이 표시됩니다.  `Microsoft.Office.Interop.Excel` 및 `Microsoft.Office.Interop.Word`는 목록에 포함되어 있지 않습니다.  프로젝트에 필요한 형식을 어셈블리로 가져왔기 때문에 PIA에 대한 참조는 필요하지 않으므로  배포를 손쉽게 수행할 수 있습니다.  PIA는 사용자의 컴퓨터에 없어도 되며 응용 프로그램에서 특정 PIA 버전을 배포할 필요가 없으므로 필요한 PIA가 모든 버전에 있다면 여러 Office 버전에서 사용하도록 응용 프로그램을 설계할 수 있습니다.  
  
     PIA를 배포할 필요가 없으므로 이전 버전을 비롯한 여러 Office 버전에서 사용 가능한 응용 프로그램을 고급 시나리오에서 만들 수 있습니다.  그러나 사용 중인 Office 버전에서 제공되지 않는 API를 코드에서 사용하지 않는 경우에만 이러한 방식이 작동합니다.  특정 API가 이전 버전에서 제공되었는지 여부를 항상 명확하게 파악할 수 있는 것은 아니므로 이전 버전의 Office는 사용하지 않는 것이 좋습니다.  
  
    > [!NOTE]
    >  Office 2003 이전 버전에서는 PIA가 게시되지 않았습니다.  그러므로 Office 2002 이하 버전에 대해 interop 어셈블리를 생성하려면 COM 참조를 가져와야 합니다.  
  
6.  매니페스트 창과 어셈블리 창을 닫습니다.  
  
### PIA 종속성을 복원하려면  
  
1.  **솔루션 탐색기**에서 **모든 파일 표시** 단추를 클릭하고  **References** 폴더를 선택한 다음 **Microsoft.Office.Interop.Excel**을 선택합니다.  **속성** 창을 표시하려면 F4 키를 누릅니다.  
  
2.  **속성** 창에서 **Interop 형식 포함** 속성을 **True**에서 **False**로 변경합니다.  
  
3.  `Microsoft.Office.Interop.Word`에 대해 이 절차의 1\-2단계를 반복합니다.  
  
4.  C\#에서 `DisplayInExcel` 메서드 끝의 `Autofit`에 대한 두 호출을 주석 처리합니다.  
  
5.  F5 키를 눌러 프로젝트가 제대로 실행되는지 확인합니다.  
  
6.  이전 절차의 1\-3 단계를 반복하여 어셈블리 창을 엽니다.  `Microsoft.Office.Interop.Word` 및 `Microsoft.Office.Interop.Excel`이 포함된 어셈블리 목록에 더 이상 표시되지 않습니다.  
  
7.  **MANIFEST** 아이콘을 두 번 클릭하고 참조되는 어셈블리 목록을 스크롤합니다.  `Microsoft.Office.Interop.Word` 및 `Microsoft.Office.Interop.Excel`이 모두 목록에 있음을 확인할 수 있습니다.  응용 프로그램에서 Excel 및 Word PIA를 참조하며 **Interop 형식 포함** 속성이 **False**로 설정되어 있으므로 두 어셈블리가 모두 최종 사용자의 컴퓨터에 있어야 합니다.  
  
8.  Visual Studio의 **빌드** 메뉴에서 **솔루션 정리**를 클릭하여 완성된 프로젝트를 정리합니다.  
  
## 참고 항목  
 [Auto\-Implemented Properties](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md)   
 [자동으로 구현된 속성](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)   
 [Collection Initializers](../../../visual-basic/reference/command-line-compiler/index.md)   
 [개체 및 컬렉션 이니셜라이저](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)   
 [Optional Parameters](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)   
 [Passing Arguments by Position and by Name](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)   
 [명명된 인수 및 선택적 인수](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)   
 [Early and Late Binding](../../../visual-basic/programming-guide/language-features/early-late-binding/early-and-late-binding.md)   
 [동적](../../../csharp/language-reference/keywords/dynamic.md)   
 [유형 동적 사용](../../../csharp/programming-guide/types/using-type-dynamic.md)   
 [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)   
 [람다 식](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)   
 [방법: COM Interop 프로그래밍에서 인덱싱된 속성 사용](../../../csharp/programming-guide/interop/how-to-use-indexed-properties-in-com-interop-rogramming.md)   
 [연습: Microsoft Office 어셈블리의 형식 정보 포함](../Topic/Walkthrough:%20Embedding%20Type%20Information%20from%20Microsoft%20Office%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)   
 [연습: 관리되는 어셈블리의 형식 포함](../Topic/Walkthrough:%20Embedding%20Types%20from%20Managed%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)   
 [연습: Excel용 첫 VSTO 추가 기능 만들기](../Topic/Walkthrough:%20Creating%20Your%20First%20VSTO%20Add-in%20for%20Excel.md)   
 [COM Interop](../../../visual-basic/programming-guide/com-interop/index.md)   
 [상호 운용성](../../../csharp/programming-guide/interop/interoperability.md)