---
title: "Walkthrough: Calling Windows APIs (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "DLLs, calling"
  - "Windows API, walkthroughs"
  - "platform invoke, walkthroughs"
  - "API calls, walkthroughs [Visual Basic]"
  - "Windows API, calling"
  - "walkthroughs [Visual Basic], API calls"
  - "DllImport attribute, calling Windows API"
  - "Declare statement, declaring DLL functions"
ms.assetid: 9280ca96-7a93-47a3-8d01-6d01be0657cb
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# Walkthrough: Calling Windows APIs (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Windows API는 Windows 운영 체제의 일부인 DLL\(동적 연결 라이브러리\)입니다.  직접 프로시저를 작성하기 어려울 때 Windows API를 사용하여 작업을 수행할 수 있습니다.  예를 들어, Windows가 제공하는 `FlashWindowEx` 함수를 사용하여 응용 프로그램의 제목 표시줄을 밝은 음영과 어두운 음영 중에서 선택적으로 표시할 수 있습니다.  
  
 Windows API에는 바로 사용할 수 있는 여러 가지 유용한 함수가 포함되어 있기 때문에 이를 코드 작성에 사용하면 개발 시간을 절약할 수 있다는 장점이 있습니다.  단점은, 문제가 발생할 경우 Windows API는 처리 및 문제 해결에 어려움이 있다는 점입니다.  
  
 Windows API는 특별한 상호 운용성 범주를 나타냅니다.  Windows API는 관리 코드를 사용하지 않고 형식 라이브러리가 기본 제공되지 않으며 Visual Studio에서 사용되는 것과 다른 데이터 형식을 사용합니다.  이러한 차이점과 Windows API는 COM 개체가 아니라는 점 때문에 Windows API와 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] 사이의 상호 운용성은 플랫폼 호출\(또는 Pinvoke\)을 통하여 수행됩니다.  플랫폼 호출은 관리 코드가, DLL로 구현되는 관리되지 않는 함수를 호출할 수 있는 서비스입니다.  자세한 내용은 [관리되지 않는 DLL 함수 사용](../Topic/Consuming%20Unmanaged%20DLL%20Functions.md)을 참조하십시오.  `Declare` 문을 사용하거나 `DllImport` 특성을 빈 프로시저에 적용하는 방법으로 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서 PInvoke를 사용할 수 있습니다.  
  
 과거에는 Windows API 호출이 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 프로그래밍에서 가장 중요한 부분이었으나 [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong-md.md)]에서는 거의 필요하지 않습니다.  가능하면 항상 Windows API 호출 대신 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)]에서 관리 코드를 사용하여 작업을 수행해야 합니다.  이 연습에서는 Windows API를 사용해야 하는 상황에 어떠한 사항이 필요한지에 대해 설명합니다.  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
## Declare를 사용한 API 호출  
 Windows API를 호출하는 가장 일반적인 방법은 `Declare` 문을 사용하는 것입니다.  
  
#### DLL 프로시저를 선언하려면  
  
1.  호출할 함수의 이름, 관련 인수, 인수 형식 및 반환 값, 함수가 포함된 DLL의 이름 및 위치를 결정합니다.  
  
    > [!NOTE]
    >  Windows API에 대한 자세한 내용은 Platform SDK Windows API의 Win32 SDK 문서를 참조하십시오.  Windows API가 사용하는 상수에 대한 자세한 내용은 Platform SDK에 들어 있는 Windows.h와 같은 헤더 파일을 참조하십시오.  
  
2.  **파일** 메뉴에서 **새로 만들기**를 클릭한 다음 **프로젝트**를 클릭하여 새 Windows 응용 프로그램 프로젝트를 엽니다.  **새 프로젝트** 대화 상자가 나타납니다.  
  
3.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 프로젝트 템플릿 목록에서 **Windows 응용 프로그램**을 선택합니다.  새 프로젝트가 표시됩니다.  
  
4.  DLL을 사용할 클래스나 모듈에 다음 `Declare` 함수를 추가합니다.  
  
     [!code-vb[VbVbalrInterop#9](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_1.vb)]  
  
### Declare 문을 구성하는 요소  
 `Declare` 문에는 다음과 같은 요소가 포함됩니다.  
  
#### Auto 한정자  
 `Auto` 한정자는 런타임에 공용 언어 런타임 규칙에 따라 메서드 이름\(또는 지정된 경우 별칭 이름\)을 기준으로 문자열을 변환하도록 지시합니다.  
  
#### Lib 및 Alias 키워드  
 `Function` 키워드 다음에 오는 이름은 사용자 프로그램이 가져온 함수에 액세스하는 데 사용되는 이름입니다.  이는 사용자가 호출하는 함수의 실제 이름과 같은 이름일 수도 있고, 올바른 프로시저 이름을 사용한 다음 `Alias` 키워드를 사용하여 호출하는 함수의 실제 이름을 지정할 수도 있습니다.  
  
 `Lib` 키워드 및 그 뒤에 호출하는 함수가 포함된 DLL의 이름과 위치를 차례로 지정합니다.  Windows 시스템 디렉터리에 있는 파일의 경로는 지정하지 않아도 됩니다.  
  
 호출하는 함수의 이름이 올바른 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 프로시저 이름이 아니거나 사용자 응용 프로그램의 다른 항목 이름과 충돌할 경우 `Alias` 키워드를 사용합니다.  `Alias`는 호출되는 함수의 실제 이름을 나타냅니다.  
  
#### 인수 및 데이터 형식 선언  
 인수 및 인수의 데이터 형식을 선언합니다.  Windows가 사용하는 데이터 형식은 Visual Studio 데이터 형식과 일치하지 않기 때문에 이러한 형식 선언은 어려울 수 있습니다.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]은 인수를 호환되는 데이터 형식으로 변환하는 *마샬링*이라는 프로세스를 통하여 많은 작업을 수행합니다.  <xref:System.Runtime.InteropServices> 네임스페이스에 정의된 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 특성을 사용하여 인수가 마샬링되는 방법을 명시적으로 제어할 수 있습니다.  
  
> [!NOTE]
>  이전 버전의 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 매개 변수 `As Any`를 선언할 수 있었습니다. 즉, 어떠한 데이터 형식의 데이터도 사용할 수 있었습니다.  그러나 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 모든 `Declare` 문에 특정 데이터 형식을 사용해야 합니다.  
  
#### Windows API 상수  
 일부 인수는 여러 개의 상수가 결합되어 구성됩니다.  예를 들어, 연습에 나온 `MessageBox` API는 메시지 상자의 표시 방법을 제어하는 `Typ`라는 정수 인수를 허용합니다.  WinUser.h 파일의 `#define` 문을 보면 이러한 상수의 숫자 값을 확인할 수 있습니다.  숫자 값은 일반적으로 16진수로 표시되므로 계산기를 사용하여 값을 모두 더한 뒤 10진수로 변환하면 됩니다.  예를 들어, 감탄 스타일 `MB_ICONEXCLAMATION` 0x00000030과 예\/아니요 스타일 `MB_YESNO` 0x00000004의 상수를 결합하려는 경우 두 숫자를 더하여 0x00000034\(또는 10진수로 52\)를 구할 수 있습니다.  10진수 결과를 직접 사용할 수도 있지만 응용 프로그램에서 값을 상수로 선언한 다음 `Or` 연산자를 사용하여 결합하는 것이 더 좋은 방법입니다.  
  
###### Windows API 호출에 사용할 상수를 선언하려면  
  
1.  사용자가 호출하는 Windows 함수에 대한 문서를 참조하여  사용되는 상수 이름과 해당 상수에 대한 숫자 값이 들어 있는 .h 파일의 이름을 확인합니다.  
  
2.  메모장 등의 텍스트 편집기를 사용하여 헤더\(.h\) 파일의 내용을 검토하고 사용 중인 상수와 연관된 값을 찾습니다.  예를 들어, `MessageBox` API는 `MB_ICONQUESTION` 상수를 사용하여 메시지 상자에 물음표를 표시합니다.  `MB_ICONQUESTION`에 대한 정의는 WinUser.h에 다음과 같이 나타납니다.  
  
     `#define MB_ICONQUESTION             0x00000020L`  
  
3.  해당하는 `Const` 문을 클래스나 모듈에 추가하여 응용 프로그램에서 이러한 상수를 사용할 수 있도록 만듭니다.  예를 들면 다음과 같습니다.  
  
     [!code-vb[VbVbalrInterop#11](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_2.vb)]  
  
###### DLL 프로시저를 호출하려면  
  
1.  `Button1`이라는 단추를 프로젝트의 시작 폼에 추가한 다음 두 번 클릭하여 해당 코드를 표시합니다.  단추에 대한 이벤트 처리기가 표시됩니다.  
  
2.  추가한 단추에 대한 `Click` 이벤트 처리기에 코드를 추가하여 프로시저를 호출하고 적절한 인수를 제공합니다.  
  
     [!code-vb[VbVbalrInterop#12](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_3.vb)]  
  
3.  F5 키를 눌러 프로젝트를 실행합니다.  **Yes**와 **No**의 두 응답 단추가 있는 메시지 상자가 표시됩니다.  둘 중 하나를 선택하십시오.  
  
#### 데이터 마샬링  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서 자동으로 Windows API 호출에 사용되는 매개 변수 및 반환 값의 데이터 형식을 변환하지만, `MarshalAs` 특성을 사용하여 API에 필요한 관리되지 않은 데이터 형식을 명시적으로 지정할 수도 있습니다.  interop 마샬링에 대한 자세한 내용은 [Interop 마샬링](../Topic/Interop%20Marshaling.md)을 참조하십시오.  
  
###### API 호출에서 Declare 및 MarshalAs를 사용하려면  
  
1.  호출할 함수의 이름과 해당 인수, 데이터 형식 및 반환 값을 결정합니다.  
  
2.  `MarshalAs` 특성에 쉽게 액세스할 수 있도록 하려면 다음 예제와 같이 `Imports` 문을 해당 클래스 또는 모듈 코드의 맨 위에 추가합니다.  
  
     [!code-vb[VbVbalrInterop#13](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_4.vb)]  
  
3.  가져온 함수에 대한 함수 프로토타입을 사용 중인 클래스나 모듈에 추가하고 `MarshalAs` 특성을 매개 변수 또는 반환 값에 적용합니다.  다음 예제에서 `void*` 형식을 예상하는 API 호출은 `AsAny`로 마샬링됩니다.  
  
     [!code-vb[VbVbalrInterop#14](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_5.vb)]  
  
## DllImport를 사용한 API 호출  
 `DllImport` 특성은 형식 라이브러리 없이 DLL에서 함수를 호출하는 두 번째 방법을 제공합니다.  `DllImport`는 함수의 호출 방법을 보다 잘 제어할 수 있는 것 외에는 `Declare` 문과 거의 동일합니다.  
  
 호출이 공유\(*정적*이라고도 함\) 메서드를 참조하는 한 대부분의 Windows API 호출에 `DllImport`를 사용할 수 있습니다.  클래스 인스턴스를 필요로 하는 메서드는 사용할 수 없습니다.  `Declare` 문과는 달리 `DllImport` 호출에서는 `MarshalAs` 특성을 사용할 수 없습니다.  
  
#### DllImport 특성을 사용하여 Windows API를 호출하려면  
  
1.  **파일** 메뉴에서 **새로 만들기**를 클릭한 다음 **프로젝트**를 클릭하여 새 Windows 응용 프로그램 프로젝트를 엽니다.  **새 프로젝트** 대화 상자가 나타납니다.  
  
2.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 프로젝트 템플릿 목록에서 **Windows 응용 프로그램**을 선택합니다.  새 프로젝트가 표시됩니다.  
  
3.  `Button2`라는 단추를 시작 폼에 추가합니다.  
  
4.  `Button2`를 두 번 클릭하여 해당 폼에 대한 코드 보기를 엽니다.  
  
5.  `DllImport`에 쉽게 액세스할 수 있도록 하려면, 시작 폼 클래스 코드의 맨 위에 `Imports` 문을 추가합니다.  
  
     [!code-vb[VbVbalrInterop#13](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_4.vb)]  
  
6.  폼에 대한 `End Class` 문 앞에 빈 함수를 선언하고 함수 이름을 `MoveFile`로 지정합니다.  
  
7.  `Public` 및 `Shared` 한정자를 함수 선언에 적용하고 Windows API 함수가 사용하는 인수를 기반으로 `MoveFile`에 대한 매개 변수를 설정합니다.  
  
     [!code-vb[VbVbalrInterop#16](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_6.vb)]  
  
     함수에는 임의의 올바른 프로시저 이름이 포함될 수 있고 `DllImport` 특성은 DLL에서의 이름을 지정합니다.  또한 함수가 매개 변수 및 반환 값에 대한 상호 운용성 마샬링을 처리하므로 사용자는 API가 사용하는 데이터 형식과 비슷한 Visual Studio 데이터 형식을 선택할 수 있습니다.  
  
8.  `DllImport` 특성을 빈 함수에 적용합니다.  첫 번째 매개 변수는 호출하는 함수를 포함하는 DLL의 이름과 위치입니다.  Windows 시스템 디렉터리에 있는 파일의 경로는 지정하지 않아도 됩니다.  두 번째 매개 변수는 Windows API에서 함수의 이름을 지정하는 명명된 인수입니다.  이 예제에서 `DllImport` 특성은 `MoveFile`에 대한 호출이 KERNEL32.DLL의 `MoveFileW`로 전달되도록 합니다.  `MoveFileW` 메서드는 파일을 `src` 경로에서 `dst` 경로로 복사합니다.  
  
     [!code-vb[VbVbalrInterop#17](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_7.vb)]  
  
9. `Button2_Click` 이벤트 처리기에 코드를 추가하여 함수를 호출합니다.  
  
     [!code-vb[VbVbalrInterop#18](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_8.vb)]  
  
10. Test.txt라는 이름으로 파일을 만들어 하드 드라이브의 C:\\Tmp 디렉터리에 저장합니다.  필요하면 Tmp 디렉터리를 만드십시오.  
  
11. F5 키를 눌러 응용 프로그램을 시작합니다.  기본 폼이 나타납니다.  
  
12. **Button2**를 클릭합니다.  파일이 이동된 경우 "The file was moved successfully."라는 메시지가 표시됩니다.  
  
## 참고 항목  
 <xref:System.Runtime.InteropServices.DllImportAttribute>   
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)   
 [Auto](../../../visual-basic/language-reference/modifiers/auto.md)   
 [Alias](../../../visual-basic/language-reference/statements/alias-clause.md)   
 [COM Interop](../../../visual-basic/programming-guide/com-interop/index.md)   
 [관리 코드에서 프로토타입 만들기](../Topic/Creating%20Prototypes%20in%20Managed%20Code.md)   
 [콜백 메서드로 대리자 마샬링](../Topic/Marshaling%20a%20Delegate%20as%20a%20Callback%20Method.md)