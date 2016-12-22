---
title: "연습: 동적 개체 만들기 및 사용(C# 및 Visual Basic) | Microsoft Docs"
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
  - "동적 개체"
  - "동적 개체[C#]"
  - "동적 개체[Visual Basic]"
ms.assetid: 568f1645-1305-4906-8625-5d77af81e04f
caps.latest.revision: 22
caps.handback.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 연습: 동적 개체 만들기 및 사용(C# 및 Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

동적 개체는 속성 및 메서드 등의 멤버를 컴파일 타임이 아니라 런타임에 노출합니다.  따라서 사용자는 정적 형식과 일치하지 않는 구조체를 다루는 개체를 생성할 수 있습니다.  예를 들어, 유효한 HTML 태그 요소 및 특성의 조합을 포함하는 HTML DOM\(문서 개체 모델\)을 참조하는 데 동적 개체를 사용할 수 있습니다.  각 HTML 문서는 서로 다르기 때문에 특정 HTML 문서에 대한 멤버는 런타임에 결정됩니다.  HTML 요소의 특성을 참조하는 일반적인 방법은 해당 요소의 `GetProperty` 메서드에 특성 이름을 전달하는 것입니다.  HTML 요소 `<div id="Div1">`의 `id` 특성을 참조하려면 먼저 `<div>` 요소에 대한 참조를 가져온 다음 `divElement.GetProperty("id")`를 사용합니다.  이와 달리 동적 개체를 사용하면 `id` 특성을 `divElement.id`로 참조할 수 있습니다.  
  
 또한 동적 개체에서는 IronPython 및 IronRuby와 같은 동적 언어에 편리하게 액세스할 수 있습니다.  동적 개체를 사용하면 런타임에 해석되는 동적 스크립트를 참조할 수 있습니다.  
  
 동적 개체는 런타임에 바인딩을 사용하여 참조합니다.  C\#에서는 런타임에 바인딩되는 개체의 형식을 `dynamic`으로 지정할 수 있고,  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서는 런타임에 바인딩되는 개체의 형식을 `Object`로 지정할 수 있습니다.  자세한 내용은 [동적](../../../csharp/language-reference/keywords/dynamic.md) 및 [Early and Late Binding](../../../visual-basic/programming-guide/language-features/early-late-binding/early-and-late-binding.md)를 참조하십시오.  
  
 <xref:System.Dynamic?displayProperty=fullName> 네임스페이스의 클래스를 사용하면 사용자 지정 동적 개체를 만들 수 있습니다.  예를 들어, <xref:System.Dynamic.ExpandoObject>를 만들고 해당 개체의 멤버를 런타임에 지정할 수 있습니다.  또한 <xref:System.Dynamic.DynamicObject> 클래스를 상속하는 사용자 고유의 형식을 만들 수도 있습니다.  그런 다음 <xref:System.Dynamic.DynamicObject> 클래스의 멤버를 재정의하여 런타임 동적 기능을 제공할 수 있습니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   동적으로 텍스트 파일의 내용을 개체의 속성으로 노출하는 사용자 지정 개체 만들기  
  
-   `IronPython` 라이브러리를 사용하는 프로젝트 만들기  
  
## 사전 요구 사항  
 이 연습을 완료하려면 .NET 4.0용 IronPython 2.6.1이 필요합니다.  [CodePlex](http://go.microsoft.com/fwlink/?LinkId=187223)에서 .NET 4.0용 IronPython 2.6.1을 다운로드할 수 있습니다.  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
## 사용자 지정 동적 개체 만들기  
 이 연습에서 만들 첫 번째 프로젝트에서는 텍스트 파일의 내용을 검색하는 사용자 지정 동적 개체를 정의합니다.  검색할 텍스트는 동적 속성의 이름으로 지정됩니다.  예를 들어, 호출 코드에서 `dynamicFile.Sample`을 지정한 경우 동적 클래스는 해당 파일에서 "Sample"로 시작하는 모든 줄이 포함된 문자열의 제네릭 목록을 반환합니다.  검색에서는 대\/소문자를 구분하지 않습니다.  또한 동적 클래스에서는 선택적 인수 두 개를 지원합니다.  첫 번째 인수는 검색 옵션 열거형 값으로, 동적 클래스가 일치 항목을 줄의 시작 위치, 끝 위치 또는 모든 위치에서 검색하도록 지정합니다.  두 번째 인수는 검색 전에 동적 클래스가 각 줄에서 선행 및 후행 공백을 잘라내도록 지정합니다.  예를 들어, 호출 코드에서 `dynamicFile.Sample(StringSearchOption.Contains)`를 지정한 경우 동적 클래스는 줄의 모든 위치에서 "Sample"을 검색합니다.  호출 코드에서 `dynamicFile.Sample(StringSearchOption.StartsWith, false)`를 지정한 경우에는 동적 클래스가 각 줄의 시작 위치에서 "Sample"을 검색하고 선행 및 후행 공백은 제거하지 않습니다.  동적 클래스의 기본 동작은 각 줄의 시작 위치에서 일치 항목을 검색하고 선행 및 후행 공백을 제거하는 것입니다.  
  
#### 사용자 지정 동적 클래스를 만들려면  
  
1.  [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]를 시작합니다.  
  
2.  **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.  
  
3.  **새 프로젝트** 대화 상자의 **프로젝트 형식** 창에서 **Windows**가 선택되었는지 확인합니다.  **템플릿** 창에서 **콘솔 응용 프로그램**을 선택합니다.  **이름** 상자에 `DynamicSample`을 입력한 다음 **확인**을 클릭합니다.  새 프로젝트가 만들어집니다.  
  
4.  DynamicSample 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가**를 가리킨 다음 **클래스**를 클릭합니다.  **이름** 상자에 `ReadOnlyFile`을 입력한 다음 **확인**을 클릭합니다.  ReadOnlyFile 클래스를 포함하는 새 파일이 추가됩니다.  
  
5.  ReadOnlyFile.cs 또는 ReadOnlyFile.vb 파일 맨 위에 다음 코드를 추가하여 <xref:System.IO?displayProperty=fullName> 및 <xref:System.Dynamic?displayProperty=fullName> 네임스페이스를 가져옵니다.  
  
     [!code-cs[VbDynamicWalkthrough#1](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_1.cs)]
     [!code-vb[VbDynamicWalkthrough#1](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_1.vb)]  
  
6.  사용자 지정 동적 개체에서는 열거형을 사용하여 검색 조건을 결정합니다.  클래스 문 이전에 다음 열거형 정의를 추가합니다.  
  
     [!code-cs[VbDynamicWalkthrough#2](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_2.cs)]
     [!code-vb[VbDynamicWalkthrough#2](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_2.vb)]  
  
7.  `DynamicObject` 클래스를 상속하도록 다음 코드 예제와 같이 클래스 문을 업데이트합니다.  
  
     [!code-cs[VbDynamicWalkthrough#3](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_3.cs)]
     [!code-vb[VbDynamicWalkthrough#3](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_3.vb)]  
  
8.  `ReadOnlyFile` 클래스에 다음 코드를 추가하여 파일 경로를 나타내는 전용 필드 및 `ReadOnlyFile` 클래스의 생성자를 정의합니다.  
  
     [!code-cs[VbDynamicWalkthrough#4](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_4.cs)]
     [!code-vb[VbDynamicWalkthrough#4](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_4.vb)]  
  
9. 다음 `GetPropertyValue` 메서드를 `ReadOnlyFile` 클래스에 추가합니다.  `GetPropertyValue` 메서드는 검색 조건을 입력으로 사용하여 텍스트 파일에서 검색 조건과 일치하는 줄을 반환합니다.  `ReadOnlyFile` 클래스에서 제공하는 동적 메서드는 `GetPropertyValue` 메서드를 호출하여 각각의 결과를 검색합니다.  
  
     [!code-cs[VbDynamicWalkthrough#5](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_5.cs)]
     [!code-vb[VbDynamicWalkthrough#5](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_5.vb)]  
  
10. `GetPropertyValue` 메서드 이후에 다음 코드를 추가하여 <xref:System.Dynamic.DynamicObject> 클래스의 <xref:System.Dynamic.DynamicObject.TryGetMember%2A> 메서드를 재정의합니다.  동적 클래스의 멤버를 요청했지만 인수가 지정되지 않은 경우 <xref:System.Dynamic.DynamicObject.TryGetMember%2A> 메서드가 호출됩니다.  `binder` 인수는 참조되는 멤버에 대한 정보를 포함하고, `result` 인수는 지정된 멤버에 대해 반환되는 결과를 참조합니다.  <xref:System.Dynamic.DynamicObject.TryGetMember%2A> 메서드는 부울 값을 반환합니다. 요청된 멤버가 있으면 `true`를 반환하고 그렇지 않으면 `false`를 반환합니다.  
  
     [!code-cs[VbDynamicWalkthrough#6](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_6.cs)]
     [!code-vb[VbDynamicWalkthrough#6](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_6.vb)]  
  
11. `TryGetMember` 메서드 이후에 다음 코드를 추가하여 <xref:System.Dynamic.DynamicObject> 클래스의 <xref:System.Dynamic.DynamicObject.TryInvokeMember%2A> 메서드를 재정의합니다.  동적 클래스의 멤버를 요청하고 인수를 지정한 경우 <xref:System.Dynamic.DynamicObject.TryInvokeMember%2A> 메서드가 호출됩니다.  `binder` 인수는 참조되는 멤버에 대한 정보를 포함하고, `result` 인수는 지정된 멤버에 대해 반환되는 결과를 참조합니다.  `args` 인수는 해당 멤버에 전달되는 인수 배열을 포함합니다.  <xref:System.Dynamic.DynamicObject.TryInvokeMember%2A> 메서드는 부울 값을 반환합니다. 요청된 멤버가 있으면 `true`를 반환하고 그렇지 않으면 `false`를 반환합니다.  
  
     `TryInvokeMember` 메서드의 사용자 지정 버전에서는 첫 번째 인수가 이전 단계에서 정의한 `StringSearchOption` 열거형의 값인 것으로 예상하고,  `TryInvokeMember` 메서드에서는 두 번째 인수가 부울 값인 것으로 예상합니다.  인수 한 개 또는 두 개가 유효한 값인 경우 인수가 `GetPropertyValue` 메서드로 전달되고 결과를 검색합니다.  
  
     [!code-cs[VbDynamicWalkthrough#7](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_7.cs)]
     [!code-vb[VbDynamicWalkthrough#7](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_7.vb)]  
  
12. 파일을 저장한 후 닫습니다.  
  
#### 샘플 텍스트 파일을 만들려면  
  
1.  DynamicSample 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가**를 가리킨 다음 **새 항목**을 클릭합니다.  **설치된 템플릿** 창에서 **일반**을 선택하고 **텍스트 파일** 템플릿을 선택합니다.  기본 이름인 TextFile1.txt를 **이름** 상자에 그대로 두고 **추가**를 클릭합니다.  새 텍스트 파일이 프로젝트에 추가됩니다.  
  
2.  다음 텍스트를 TextFile1.txt 파일에 복사합니다.  
  
    ```  
    List of customers and suppliers  
  
    Supplier: Lucerne Publishing (http://www.lucernepublishing.com/)  
    Customer: Preston, Chris  
    Customer: Hines, Patrick  
    Customer: Cameron, Maria  
    Supplier: Graphic Design Institute (http://www.graphicdesigninstitute.com/)   
    Supplier: Fabrikam, Inc. (http://www.fabrikam.com/)   
    Customer: Seubert, Roxanne  
    Supplier: Proseware, Inc. (http://www.proseware.com/)   
    Customer: Adolphi, Stephan  
    Customer: Koch, Paul  
    ```  
  
3.  파일을 저장한 후 닫습니다.  
  
#### 사용자 지정 동적 개체를 사용하는 샘플 응용 프로그램을 만들려면  
  
1.  **솔루션 탐색기**에서 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]을 사용 중이면 Module1.vb 파일을 두 번 클릭하고 Visual C\#을 사용 중이면 Program.cs 파일을 두 번 클릭합니다.  
  
2.  다음 코드를 Main 프로시저에 추가하여 TextFile1.txt 파일에 대한 `ReadOnlyFile` 클래스의 인스턴스를 만듭니다.  이 코드에서는 런타임에 바인딩을 사용하여 동적 멤버를 호출하고, 문자열 "Customer"가 포함된 텍스트 줄을 검색합니다.  
  
     [!code-cs[VbDynamicWalkthrough#8](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_8.cs)]
     [!code-vb[VbDynamicWalkthrough#8](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_8.vb)]  
  
3.  파일을 저장한 다음 Ctrl\+F5를 눌러 응용 프로그램을 빌드 및 실행합니다.  
  
## 동적 언어 라이브러리 호출  
 이 연습에서 만드는 다음 프로젝트에서는 동적 언어 IronPython으로 작성된 라이브러리에 액세스합니다.  이 프로젝트를 만들려면 .NET 4.0용 IronPython 2.6.1이 설치되어 있어야 합니다.  [CodePlex](http://go.microsoft.com/fwlink/?LinkId=187223)에서 .NET 4.0용 IronPython 2.6.1을 다운로드할 수 있습니다.  
  
#### 사용자 지정 동적 클래스를 만들려면  
  
1.  [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]의 **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.  
  
2.  **새 프로젝트** 대화 상자의 **프로젝트 형식** 창에서 **Windows**가 선택되었는지 확인합니다.  **템플릿** 창에서 **콘솔 응용 프로그램**을 선택합니다.  **이름** 상자에 `DynamicIronPythonSample`을 입력하고 **확인**을 클릭합니다.  새 프로젝트가 만들어집니다.  
  
3.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]을 사용하는 경우 DynamicIronPythonSample 프로젝트를 마우스 오른쪽 단추로 클릭한 다음 **속성**을 클릭합니다.  **참조** 탭을 클릭합니다.  **추가** 단추를 클릭합니다.  Visual C\#을 사용하는 경우 **솔루션 탐색기**에서 **References** 폴더를 마우스 오른쪽 단추로 클릭한 다음 **참조 추가**를 클릭합니다.  
  
4.  **찾아보기** 탭에서 IronPython 라이브러리가 설치된 폴더를 찾습니다.  예를 들면 C:\\Program Files\\IronPython 2.6 for .NET 4.0을 찾습니다.  **IronPython.dll**, **IronPython.Modules.dll**, **Microsoft.Scripting.dll** 및 **Microsoft.Dynamic.dll** 라이브러리를 선택합니다.  **확인**을 클릭합니다.  
  
5.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]을 사용하는 경우에는 Module1.vb 파일을 편집하고  Visual C\#을 사용하는 경우에는 Program.cs 파일을 편집합니다.  
  
6.  파일 맨 위에 다음 코드를 추가하여 IronPython 라이브러리에서 `Microsoft.Scripting.Hosting` 및 `IronPython.Hosting` 네임스페이스를 가져옵니다.  
  
     [!code-cs[VbDynamicWalkthroughIronPython#1](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_9.cs)]
     [!code-vb[VbDynamicWalkthroughIronPython#1](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_9.vb)]  
  
7.  Main 메서드에서 IronPython 라이브러리를 호스팅할 새 `Microsoft.Scripting.Hosting.ScriptRuntime` 개체를 만드는 다음 코드를 추가합니다.  `ScriptRuntime` 개체는 IronPython 라이브러리 모듈인 random.py를 로드합니다.  
  
     [!code-cs[VbDynamicWalkthroughIronPython#2](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_10.cs)]
     [!code-vb[VbDynamicWalkthroughIronPython#2](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_10.vb)]  
  
8.  random.py 모듈을 로드하는 코드 뒤에 정수 배열을 만드는 다음 코드를 추가합니다.  배열은 random.py 모듈의 `shuffle` 메서드로 전달됩니다. 이 메서드는 배열 값을 무작위로 정렬합니다.  
  
     [!code-cs[VbDynamicWalkthroughIronPython#3](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_11.cs)]
     [!code-vb[VbDynamicWalkthroughIronPython#3](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_11.vb)]  
  
9. 파일을 저장한 다음 Ctrl\+F5를 눌러 응용 프로그램을 빌드 및 실행합니다.  
  
## 참고 항목  
 <xref:System.Dynamic?displayProperty=fullName>   
 <xref:System.Dynamic.DynamicObject?displayProperty=fullName>   
 [유형 동적 사용](../../../csharp/programming-guide/types/using-type-dynamic.md)   
 [Early and Late Binding](../../../visual-basic/programming-guide/language-features/early-late-binding/early-and-late-binding.md)   
 [동적](../../../csharp/language-reference/keywords/dynamic.md)   
 [\(외부 블로그\) 동적 인터페이스 구현](http://go.microsoft.com/fwlink/?LinkId=230895)