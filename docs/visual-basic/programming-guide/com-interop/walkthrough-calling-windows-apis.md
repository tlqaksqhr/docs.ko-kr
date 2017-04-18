---
title: "연습: Windows Api 호출 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- DLLs, calling
- Windows API, walkthroughs
- platform invoke, walkthroughs
- API calls, walkthroughs [Visual Basic]
- Windows API, calling
- walkthroughs [Visual Basic], API calls
- DllImport attribute, calling Windows API
- Declare statement, declaring DLL functions
ms.assetid: 9280ca96-7a93-47a3-8d01-6d01be0657cb
caps.latest.revision: 20
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
ms.openlocfilehash: 5001ccebb0a5b8cadd4e856342601506cf1d033f
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-calling-windows-apis-visual-basic"></a>연습: Windows API 호출(Visual Basic)
Windows Api는 Windows 운영 체제의 일부인 동적 연결 라이브러리 (Dll)입니다. 프로시저를 직접 작성 하기 어려운 경우 작업을 수행 하 고를 사용 합니다. Windows 라는 함수를 제공 하는 예를 들어 `FlashWindowEx` 밝은 영역과 어두운 음영을 교대로 제목 표시줄에 응용 프로그램을 만들 수 있습니다.  
  
 Windows Api를 사용 하 여 코드에서의 장점은 사용 하기 위해 대기 하 고 여러 가지 유용한 함수가 이미 작성 된 포함 하기 때문에 개발 시간을 절약할 수 있습니다. 단점은 Windows Api는 간편 하 고 철 문제가 발생할 때 어려울 수 있습니다.  
  
 Windows Api의 상호 운용성 특정 범주를 나타냅니다. Windows Api 관리 되는 코드를 사용 하지 않는, 기본 제공 라이브러리를 입력 하 고 Visual Studio와 함께 사용 되는 것과 다른 데이터 형식을 사용할 필요는 없습니다. 이러한 차이 때문에 있고 Windows Api는 COM 개체, Windows Api와의 상호 운용성 및 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 플랫폼을 사용 하 여 이루어집니다를 호출 pinvoke입니다. 플랫폼 호출 수 있도록 Dll에서 구현 하는 관리 되지 않는 함수를 호출 하는 코드를 관리 하는 서비스입니다. 자세한 내용은 참조 [관리 되지 않는 DLL 함수를 사용해](http://msdn.microsoft.com/library/eca7606e-ebfb-4f47-b8d9-289903fdc045)합니다. PInvoke를 사용할 수 있습니다 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 중 하나를 사용 하 여는 `Declare` 문 또는 적용는 `DllImport` 빈 프로시저에 대 한 특성입니다.  
  
 Windows API 호출의 중요 한 부분이 되었습니다 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 과거에서 프로그래밍, 하지만 대부분의 경우에 필요 [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)]합니다. 관리 되는 코드를 사용 해야 가능 하다 면는 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] Windows API를 호출 하는 대신 작업을 수행할 수 있습니다. 이 연습을 사용 하 여 이러한 상황에 대 한 정보를 제공 합니다. Windows Api는 필요 합니다.  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
## <a name="api-calls-using-declare"></a>API 호출을 사용 하 여 선언  
 Windows Api를 호출 하는 가장 일반적인 방법은 사용 하는 것은 `Declare` 문입니다.  
  
#### <a name="to-declare-a-dll-procedure"></a>DLL 프로시저를 선언 하려면  
  
1.  를 호출 하려면 원하는 함수 관련 인수, 인수 형식을의 이름을 확인 하 고 값 뿐만 아니라 이름 및 포함 된 DLL의 위치를 반환 합니다.  
  
    > [!NOTE]
    >  Windows Api에 대 한 자세한 내용은 플랫폼 SDK Windows API에서 Win32 SDK 설명서를 참조 합니다. Windows Api를 사용 하는 상수에 대 한 자세한 내용은 Platform SDK에 포함 된 h와 같은 헤더 파일을 검사 합니다.  
  
2.  클릭 하 여 새 Windows 응용 프로그램 프로젝트를 열고 **새로** 에 **파일** 메뉴를 클릭 한 다음 **프로젝트**합니다. **새 프로젝트** 대화 상자가 나타납니다.  
  
3.  선택 **Windows 응용 프로그램** 목록에서 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 프로젝트 템플릿이 포함 되어 있습니다. 새 프로젝트가 표시 됩니다.  
  
4.  다음 코드를 추가 `Declare` 클래스 또는 DLL을 사용 하 여 원하는 모듈에 작동 합니다.  
  
     [!code-vb[VbVbalrInterop #&9;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_1.vb)]  
  
### <a name="parts-of-the-declare-statement"></a>부분은 Declare 문  
 `Declare` 문에 다음과 같은 요소가 포함 됩니다.  
  
#### <a name="auto-modifier"></a>Auto 한정자  
 `Auto` 한정자는 런타임에 공용 언어 런타임 규칙 (또는 별칭 이름을 지정 하는 경우)에 따라 메서드 이름에 따라 문자열을 변환 하도록 지시 합니다.  
  
#### <a name="lib-and-alias-keywords"></a>Lib 및 별칭 키워드  
 다음 이름은 `Function` 키워드는 프로그램에서 가져온된 함수에 액세스 하는 이름입니다. 함수를 호출 하는 실제 이름과 동일 또는 다른 유효한 프로시저 이름 및 사용한 다음에 사용할 수는 `Alias` 키워드를 호출 하는 함수의 실제 이름을 지정 합니다.  
  
 지정 된 `Lib` 키워드와 이름 및 함수를 호출 하는 포함 하는 DLL의 위치입니다. Windows 시스템 디렉터리에 있는 파일에 대 한 경로를 지정할 필요가 없습니다.  
  
 사용 하는 `Alias` 호출 하는 함수 이름이 유효한 키워드 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 프로시저 이름 또는 응용 프로그램에서 다른 항목의 이름과 충돌 합니다. `Alias`호출 되는 함수의의 실제 이름을 나타냅니다.  
  
#### <a name="argument-and-data-type-declarations"></a>인수 및 데이터 형식 선언  
 인수 및 해당 데이터 형식을 선언 합니다. Windows에서 사용 하는 데이터 형식 Visual Studio 데이터 형식에 대응 되지 않기 때문에이 부분을 매우 어려울 수 있습니다. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]호환 되는 데이터 형식, 라고 하는 프로세스에 인수를 변환 하는 많은 작업을 수행 *마샬링*합니다. 인수를 사용 하 여 마샬링되는 방법을 명시적으로 제어할 수는 <xref:System.Runtime.InteropServices.MarshalAsAttribute>에 정의 된 특성의 <xref:System.Runtime.InteropServices>네임 스페이스.</xref:System.Runtime.InteropServices> </xref:System.Runtime.InteropServices.MarshalAsAttribute>  
  
> [!NOTE]
>  이전 버전의 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 매개 변수를 선언 하는 데 사용할 수 `As Any`, 즉 모든 데이터의 해당 데이터 형식을 사용할 수 있습니다. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]특정 데이터 형식을 사용 하 여 모든 필요한 `Declare` 문입니다.  
  
#### <a name="windows-api-constants"></a>Windows API 상수  
 일부 인수는 상수의 조합입니다. 예를 들어는 `MessageBox` 라는 정수 인수를 허용 하는이 연습에 표시 되는 API `Typ` 메시지 상자가 표시 되는 방식을 제어 하 합니다. 검사 하 여 이러한 상수 중 숫자 값을 확인할 수는 `#define` WinUser.h 파일에 있습니다. 숫자 값은&16; 진수, 일반적으로 표시는 계산기를 사용 하 여 추가 하 고&10; 진수로 변환 해야 할 수 있습니다. 예를 들어 감탄 스타일에 대 한 상수를 결합 하려면 `MB_ICONEXCLAMATION` 0x00000030 Yes/스타일 없음 `MB_YESNO` 0x00000004, 숫자를 추가 하 고 10 진수 0x00000034, 또는 52의 결과 얻을 수 있습니다. 응용 프로그램에서 상수로 이러한 값을 선언 하 고 결합 하는 것이 좋습니다&10; 진수 결과 직접 사용할 수 있지만 사용 하는 `Or` 연산자입니다.  
  
###### <a name="to-declare-constants-for-windows-api-calls"></a>Windows API 호출에 대 한 상수를 선언 하려면  
  
1.  호출 하는 Windows 함수에 대 한 설명서를 참조 하십시오. 이러한 상수에 대 한 숫자 값을 포함 하는.h 파일의 이름과 사용 되는 상수의 이름을 결정 합니다.  
  
2.  헤더 (.h) 파일의 내용을 보려면 메모장 같은 텍스트 편집기를 사용 하 고 사용 하는 상수와 관련 된 값을 찾습니다. 예를 들어는 `MessageBox` API 상수를 사용 하 여 `MB_ICONQUESTION` 메시지 상자에 물음표를 표시 합니다. 에 대 한 정의가 `MB_ICONQUESTION` WinUser.h 이며 다음과 같이 표시 됩니다.  
  
     `#define MB_ICONQUESTION             0x00000020L`  
  
3.  해당 하는 추가 `Const` 문을 클래스나 모듈 이러한 상수를 응용 프로그램에서 사용할 수 있도록 합니다. 예:  
  
     [!code-vb[VbVbalrInterop #&11;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_2.vb)]  
  
###### <a name="to-call-the-dll-procedure"></a>DLL 프로시저를 호출 하려면  
  
1.  이라는 단추를 추가 `Button1` 시작 프로젝트를 만들어 해당 코드를 보려면 두 번 클릭 합니다. 단추에 대 한 이벤트 처리기가 표시 됩니다.  
  
2.  코드를 추가 하는 `Click` 프로시저를 호출 하 고 적절 한 인수를 제공 하려면 추가한 단추에 대 한 이벤트 처리기:  
  
     [!code-vb[VbVbalrInterop #&12;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_3.vb)]  
  
3.  F5 키를 눌러 프로젝트를 실행 합니다. 메시지 상자가 모두와 함께 표시 됩니다 **예** 및 **No** 응답 단추가 있습니다. 중 하나를 클릭 합니다.  
  
#### <a name="data-marshaling"></a>데이터 마샬링  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]자동 변환 매개 변수 및 반환 값 수 있지만 Windows API 호출에 대 한 데이터 형식을 사용할 수는 `MarshalAs` 특성을 API에 필요한 관리 되지 않는 데이터 형식을 명시적으로 지정 합니다. Interop 마샬링 하는 방법에 대 한 자세한 내용은 참조 [Interop 마샬링](http://msdn.microsoft.com/library/115f7a2f-d422-4605-ab36-13a8dd28142a)합니다.  
  
###### <a name="to-use-declare-and-marshalas-in-an-api-call"></a>API 호출에 Declare 및 MarshalAs를 사용 하 여  
  
1.  해당 인수, 데이터 형식, 호출 하고자 하는 함수 이름을 확인 하 고 값을 반환 합니다.  
  
2.  에 대 한 액세스를 간소화 하는 `MarshalAs` 특성을 추가 `Imports` 클래스 또는 다음 예제와 같이 모듈에 대 한 코드의 맨 위에 문을:  
  
     [!code-vb[VbVbalrInterop #&13;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_4.vb)]  
  
3.  클래스 또는 모듈을 사용 하는 및 적용에 가져온된 함수에 대 한 함수 프로토타입을 추가 `MarshalAs` 특성을 매개 변수 또는 반환 값입니다. 다음 예제에서는 형식을 예상 하는 API 호출에서에서 `void*` 로 마샬링됩니다 `AsAny`:  
  
     [!code-vb[VbVbalrInterop #&14;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_5.vb)]  
  
## <a name="api-calls-using-dllimport"></a>DllImport를 사용 하 여 API 호출  
 `DllImport` 특성은 형식 라이브러리 없이 Dll에서 함수를 호출 하는 두 번째 방법을 제공 합니다. `DllImport`사용 하 여 거의 같습니다는 `Declare` 문은 함수를 호출 하는 방법을 보다 자세히 제어를 제공 합니다.  
  
 사용할 수 있습니다 `DllImport` 대부분 Windows API와 공유를 호출은으로 호출 (라고도 *정적*) 메서드가 있습니다. 클래스의 인스턴스를 필요로 하는 메서드를 사용할 수 없습니다. 와 달리 `Declare` 문, `DllImport` 호출을 사용할 수 없습니다는 `MarshalAs` 특성입니다.  
  
#### <a name="to-call-a-windows-api-using-the-dllimport-attribute"></a>DllImport 특성을 사용 하 여 Windows API를 호출 하려면  
  
1.  클릭 하 여 새 Windows 응용 프로그램 프로젝트를 열고 **새로** 에 **파일** 메뉴를 클릭 한 다음 **프로젝트**합니다. **새 프로젝트** 대화 상자가 나타납니다.  
  
2.  선택 **Windows 응용 프로그램** 목록에서 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 프로젝트 템플릿이 포함 되어 있습니다. 새 프로젝트가 표시 됩니다.  
  
3.  이라는 단추를 추가 `Button2` 시작 폼입니다.  
  
4.  두 번 클릭 `Button2` 폼에 대 한 코드 보기를 엽니다.  
  
5.  에 대 한 액세스를 간소화 하기 위해 `DllImport`, 추가 된 `Imports` 시작 폼 클래스에 대 한 코드의 맨 위에 문을:  
  
     [!code-vb[VbVbalrInterop #&13;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_4.vb)]  
  
6.  위의 빈 함수를 선언는 `End Class` 함수 이름을 확인 하 고 폼에 대 한 문을 `MoveFile`합니다.  
  
7.  적용 된 `Public` 및 `Shared` 함수 선언 및 매개 변수를 설정에 대 한 한정자 `MoveFile` Windows API 함수를 사용 하는 인수에 따라:  
  
     [!code-vb[VbVbalrInterop #&16;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_6.vb)]  
  
     함수 이름에는 제한이 유효한 프로시저; `DllImport` 특성 DLL의 이름을 지정 합니다. 또한 상호 운용성 마샬링 매개 변수를 처리 및 반환 값, 데이터와 마찬가지로 Visual Studio 데이터 형식을 선택할 수 있는 형식과 API가 사용 합니다.  
  
8.  적용 된 `DllImport` 특성을 빈 함수입니다. 첫 번째 매개 변수는 이름과 호출 하는 함수를 포함 하는 DLL의 위치입니다. Windows 시스템 디렉터리에 있는 파일에 대 한 경로를 지정할 필요가 없습니다. 두 번째 매개 변수는 Windows API에는 함수의 이름을 지정 하는 명명 된 인수입니다. 이 예제는 `DllImport` 특성에 대 한 호출을 강제로 `MoveFile` 전달할 `MoveFileW` KERNEL32에서. DLL입니다. `MoveFileW` 경로에서 파일을 복사 하는 메서드 `src` 경로에 `dst`합니다.  
  
     [!code-vb[VbVbalrInterop #&17;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_7.vb)]  
  
9. 코드를 추가 하는 `Button2_Click` 이벤트 처리기 함수를 호출 합니다.  
  
     [!code-vb[VbVbalrInterop #&18;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_8.vb)]  
  
10. Test.txt 파일을 만들고 하드 드라이브에 C:\Tmp 디렉터리에 배치 합니다. 필요한 경우 Tmp 디렉터리를 만듭니다.  
  
11. F5 키를 눌러 응용 프로그램을 시작합니다. 기본 폼이 나타납니다.  
  
12. 클릭 **Button2**합니다. 파일을 이동할 수 있는 경우 "파일이 성공적으로 이동" 메시지가 표시 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Runtime.InteropServices.DllImportAttribute></xref:System.Runtime.InteropServices.DllImportAttribute>   
 <xref:System.Runtime.InteropServices.MarshalAsAttribute></xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Declare 문](../../../visual-basic/language-reference/statements/declare-statement.md)   
 [자동](../../../visual-basic/language-reference/modifiers/auto.md)   
 [별칭](../../../visual-basic/language-reference/statements/alias-clause.md)   
 [COM Interop](../../../visual-basic/programming-guide/com-interop/index.md)   
 [관리 코드에서 프로토타입 만들기](http://msdn.microsoft.com/library/ecdcf25d-cae3-4f07-a2b6-8397ac6dc42d)   
 [콜백 메서드로 대리자 마샬링](http://msdn.microsoft.com/library/6ddd7866-9804-4571-84de-83f5cc017a5a)
