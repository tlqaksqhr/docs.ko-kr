---
title: '연습: Windows API 호출(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- DLLs, calling
- Windows API, walkthroughs
- platform invoke, walkthroughs
- API calls [Visual Basic], walkthroughs [Visual Basic]
- Windows API, calling
- walkthroughs [Visual Basic], API calls
- DllImport attribute, calling Windows API
- Declare statement [Visual Basic], declaring DLL functions
ms.assetid: 9280ca96-7a93-47a3-8d01-6d01be0657cb
ms.openlocfilehash: bb98d842bfe65bdf637a789fc9a8319a70cb2bc8
ms.sourcegitcommit: 869b5832b667915ac4a5dd8c86b1109ed26b6c08
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2018
ms.locfileid: "39332862"
---
# <a name="walkthrough-calling-windows-apis-visual-basic"></a>연습: Windows API 호출(Visual Basic)
Windows Api는 Windows 운영 체제의 일부인 동적 연결 라이브러리 (Dll)입니다. 프로시저를 직접 작성 하기 어려운 경우 작업을 수행 하려면 사용할 수 있습니다. Windows 라는 함수를 제공 하는 예를 들어 `FlashWindowEx` 밝은 영역과 어두운 음영을 교대로 응용 프로그램의 제목 표시줄을 만들 수 있습니다.  
  
 Windows Api를 사용 하 여 코드에서의 장점은 여러 가지 유용한 함수가 이미 작성 된 되어 대기 중인 사용할 수 있기 때문에 개발 시간을 절약할 수 있습니다. 단점은 Windows Api와 철 문제가 발생할 때 작업이 어려울 수 있습니다.  
  
 Windows Api의 상호 운용성 특수 범주를 나타냅니다. Windows Api는 관리 되는 코드를 사용 하지, 기본 제공 라이브러리를 입력 하 고 Visual Studio와 함께 사용 되는 것과 다른 데이터 형식을 사용할 필요가 없습니다. 이러한 차이점 때문 이므로 Windows Api는 COM 개체를 Windows Api와의 상호 운용성 및 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 플랫폼을 사용 하 여 수행 됩니다 호출 또는 PInvoke입니다. 플랫폼 호출 서비스는 관리 되는 Dll로 구현 되는 관리 되지 않는 함수를 호출 하는 코드입니다. 자세한 내용은 [관리 되지 않는 DLL 함수 사용](../../../framework/interop/consuming-unmanaged-dll-functions.md)합니다. 하나를 사용 하 여 Visual Basic에서 PInvoke를 사용할 수 있습니다는 `Declare` 문 또는 적용을 `DllImport` 빈 프로시저에 특성입니다.  
  
 Windows API 호출에서 중요 한 부분은 Visual Basic 이전에 프로그래밍 된 되지만 Visual Basic.NET을 사용 하 여 필요한 거의 없습니다. 가능 하면에서 관리 되는 코드를 사용 해야는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Windows API를 호출 하는 대신 작업을 수행 합니다. 이 연습에서 사용 하는 경우에 대 한 정보를 제공 합니다. Windows Api가 필요 합니다.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="api-calls-using-declare"></a>API 호출을 사용 하 여 선언  
 Windows Api를 호출 하는 가장 일반적인 방법은 사용 하는 것은 `Declare` 문입니다.  
  
#### <a name="to-declare-a-dll-procedure"></a>DLL 프로시저를 선언 하려면  
  
1.  를 호출 하려면 원하는 함수 및 인수, 인수 형식 이름을 확인 하 고 값 뿐만 아니라와 이름을 포함 하는 DLL의 위치를 반환 합니다.  
  
    > [!NOTE]
    >  Windows Api에 대 한 자세한 내용은 플랫폼 SDK Windows API에서 Win32 SDK 설명서를 참조 하세요. Windows Api를 사용 하는 상수에 대 한 자세한 내용은 플랫폼 SDK에 포함 된 Windows.h 같은 헤더 파일을 검사 합니다.  
  
2.  클릭 하 여 새 Windows 응용 프로그램 프로젝트를 엽니다 **새로 만들기** 에 **파일** 메뉴에서을 클릭 한 다음 **프로젝트**합니다. **새 프로젝트** 대화 상자가 나타납니다.  
  
3.  선택 **Windows 응용 프로그램** Visual Basic 프로젝트 템플릿 목록에서. 새 프로젝트가 표시 됩니다.  
  
4.  다음 추가 `Declare` 클래스 또는 모듈 DLL을 사용 하려는 함수:  
  
     [!code-vb[VbVbalrInterop#9](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_1.vb)]  
  
### <a name="parts-of-the-declare-statement"></a>일부는 Declare 문  
 `Declare` 문에 다음 요소가 포함 됩니다.  
  
#### <a name="auto-modifier"></a>Auto 한정자  
 `Auto` 한정자는 런타임에 공용 언어 런타임 규칙 (또는 별칭 이름을 지정 하는 경우)에 따라 메서드 이름을 기반으로 문자열을 변환 하도록 지시 합니다.  
  
#### <a name="lib-and-alias-keywords"></a>Lib 및 별칭 키워드  
 다음에는 이름이 `Function` 키워드 프로그램 사용 하 여 액세스 가져온된 함수의 이름입니다. 함수를 호출 하는 실제 이름과 동일 수 또는 다른 유효한 프로시저 이름 및 사용한 다음 사용할 수는 `Alias` 키워드를 호출 하는 함수의 실제 이름을 지정 합니다.  
  
 지정 된 `Lib` 키워드를 호출 하는 함수가 포함 된 DLL의 위치와 이름을 뒤에. Windows 시스템 디렉터리에 있는 파일의 경로를 지정할 필요가 없습니다.  
  
 사용 하 여는 `Alias` 키워드는 함수의 이름을 호출 하는 경우 유효한 Visual Basic 프로시저 이름을 없거나 응용 프로그램에서 다른 항목의 이름과 충돌 합니다. `Alias` 호출 되는 함수의의 실제 이름을 나타냅니다.  
  
#### <a name="argument-and-data-type-declarations"></a>인수 및 데이터 형식 선언  
 인수 및 해당 데이터 형식을 선언 합니다. Windows를 사용 하는 데이터 형식을 Visual Studio 데이터 형식에 대응 되지 않기 때문에이 부분을 어려울 수 있습니다. Visual Basic을 호환 되는 데이터 형식 이라고 하는 프로세스에 인수를 변환 하는 많은 작업을 수행 *마샬링*합니다. 인수를 사용 하 여 마샬링되는 방법을 명시적으로 제어할 수 있습니다.는 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 에 정의 된 특성과 <xref:System.Runtime.InteropServices> 네임 스페이스입니다.  
  
> [!NOTE]
>  이전 버전의 Visual Basic 매개 변수를 선언할 수 `As Any`, 즉 모든 데이터의 해당 데이터 형식을 사용할 수 있습니다. Visual Basic 모두에 대 한 특정 데이터 형식을 사용 해야 `Declare` 문입니다.  
  
#### <a name="windows-api-constants"></a>Windows API 상수  
 일부 인수가 상수 조합에 설명 합니다. 예를 들어 합니다 `MessageBox` 라는 정수 인수를 허용 하는이 연습에서는 표시 된 API `Typ` 메시지 상자가 표시 되는 방식을 제어 하는 합니다. 이러한 상수는 숫자 값을 검사 하 여 확인할 수 있습니다는 `#define` WinUser.h 파일의 문입니다. 숫자 값 이므로 계산기를 추가 하 고 10 진수로 변환 하는 데 사용할 수 있습니다에 일반적으로 16 진수로 표시 됩니다. 예를 들어, 느낌표 스타일에 대 한 상수를 결합 하려는 경우 `MB_ICONEXCLAMATION` 0x00000030 Yes/스타일이 없습니다 `MB_YESNO` 0x00000004, 숫자를 추가 하 고 10 진수 0x00000034를 52 개 결과 가져옵니다. 상수 응용 프로그램에서 이러한 값을 선언 하 고 결합 하는 10 진수 결과 직접 사용할 수 있지만 사용 하는 `Or` 연산자입니다.  
  
###### <a name="to-declare-constants-for-windows-api-calls"></a>Windows API 호출에 대 한 상수를 선언 하려면  
  
1.  Windows 함수를 호출 하는 설명서를 참조 하세요. 이러한 상수에 대 한 숫자 값이 포함 된.h 파일의 이름과 상수를 사용 하 여 이름을 확인 합니다.  
  
2.  헤더 (.h) 파일의 내용을 보려면 메모장과 같은 텍스트 편집기를 사용 하 고 사용 하는 상수를 사용 하 여 연결 된 값을 찾습니다. 예를 들어 합니다 `MessageBox` 상수를 사용 하는 API `MB_ICONQUESTION` 물음표 메시지 상자에 표시할 합니다. 에 대 한 정의 `MB_ICONQUESTION` WinUser.h 이며 다음과 같이 나타납니다.  
  
     `#define MB_ICONQUESTION             0x00000020L`  
  
3.  해당 추가 `Const` 문을 클래스 또는 모듈 이러한 상수를 응용 프로그램에 사용할 수 있도록 합니다. 예를 들어:  
  
     [!code-vb[VbVbalrInterop#11](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_2.vb)]  
  
###### <a name="to-call-the-dll-procedure"></a>DLL 프로시저를 호출 하려면  
  
1.  이라는 단추가 추가 `Button1` 시작 프로젝트를 만들어 해당 코드를 보려면 두 번 클릭 합니다. 단추에 대 한 이벤트 처리기 표시 됩니다.  
  
2.  코드를 추가 하 여 `Click` 프로시저를 호출 하 고 적절 한 인수를 제공 하려면 추가한 단추에 대 한 이벤트 처리기:  
  
     [!code-vb[VbVbalrInterop#12](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_3.vb)]  
  
3.  F5 키를 눌러 프로젝트를 실행 합니다. 둘 다와 함께 하는 메시지가 표시 됩니다 **예** 하 고 **No** 응답 단추입니다. 둘 중 하나를 클릭 합니다.  
  
#### <a name="data-marshaling"></a>데이터 마샬링  
 Visual Basic에는 자동으로 매개 변수 및 Windows API 호출에 대 한 반환 값의 데이터 형식 변환 하지만 사용할 수는 `MarshalAs` API 필요로 하는 관리 되지 않는 데이터 형식을 명시적으로 지정 하는 특성입니다. Interop 마샬링 하는 방법에 대 한 자세한 내용은 참조 하세요. [Interop 마샬링](../../../framework/interop/interop-marshaling.md)합니다.  
  
###### <a name="to-use-declare-and-marshalas-in-an-api-call"></a>API 호출에 선언 하 고 MarshalAs를 사용 하려면  
  
1.  데이터 형식에 해당 인수, 호출 하려는 함수의 이름을 확인 하 고 값을 반환 합니다.  
  
2.  에 대 한 액세스를 간소화 하는 `MarshalAs` 특성을 추가 `Imports` 클래스 또는 모듈의 경우 다음 예제와 같이 코드의 맨 위에 문:  
  
     [!code-vb[VbVbalrInterop#13](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_4.vb)]  
  
3.  클래스 또는 모듈을 사용 하 고 적용 하는 함수 프로토타입이 가져온된 함수를 추가 합니다 `MarshalAs` 매개 변수에 특성 또는 값을 반환 합니다. 다음 예에서 형식을 예상 하는 API 호출은 `void*` 으로 마샬링될 `AsAny`:  
  
     [!code-vb[VbVbalrInterop#14](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_5.vb)]  
  
## <a name="api-calls-using-dllimport"></a>DllImport를 사용 하 여 API 호출  
 `DllImport` 특성 없이 형식 라이브러리 Dll의 함수를 호출 하는 두 번째 방법을 제공 합니다. `DllImport` 사용 하 여 거의 동일한는 `Declare` 문은 함수를 호출 하는 방법을 보다 자세히 제어를 제공 하지만 합니다.  
  
 사용할 수 있습니다 `DllImport` 대부분의 Windows API를 사용 하 여 공유 호출은으로 호출 (라고도 *정적*) 메서드. 클래스의 인스턴스를 필요로 하는 메서드를 사용할 수 없습니다. 와 달리 `Declare` 문 `DllImport` 호출을 사용할 수 없습니다는 `MarshalAs` 특성입니다.  
  
#### <a name="to-call-a-windows-api-using-the-dllimport-attribute"></a>DllImport 특성을 사용 하 여 Windows API를 호출 하려면  
  
1.  클릭 하 여 새 Windows 응용 프로그램 프로젝트를 엽니다 **새로 만들기** 에 **파일** 메뉴에서을 클릭 한 다음 **프로젝트**합니다. **새 프로젝트** 대화 상자가 나타납니다.  
  
2.  선택 **Windows 응용 프로그램** Visual Basic 프로젝트 템플릿 목록에서. 새 프로젝트가 표시 됩니다.  
  
3.  이라는 단추가 추가 `Button2` 시작 폼입니다.  
  
4.  두 번 클릭 `Button2` 폼의 코드 보기를 엽니다.  
  
5.  에 대 한 액세스를 간소화 하기 위해 `DllImport`, 추가 `Imports` 시작 폼 클래스에 대 한 코드의 맨 위에 문:  
  
     [!code-vb[VbVbalrInterop#13](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_4.vb)]  
  
6.  위의 빈 함수를 선언 합니다 `End Class` 폼 및 함수 이름에 대 한 문을 `MoveFile`합니다.  
  
7.  적용 된 `Public` 하 고 `Shared` 함수 선언 및 매개 변수를 설정 하는 한정자 `MoveFile` Windows API 함수를 사용 하 여 인수를 기준으로:  
  
     [!code-vb[VbVbalrInterop#16](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_6.vb)]  
  
     함수 이름에는 제한이 유효한 프로시저; `DllImport` 특성 DLL의 이름을 지정 합니다. 또한 상호 운용성 마샬링 매개 변수를 처리 하 고 반환 값, Visual Studio는 데이터 형식에 데이터와 유사한를 선택할 수 있습니다는 API가 사용 됩니다.  
  
8.  적용 된 `DllImport` 빈 함수에 특성입니다. 첫 번째 매개 변수 이름 및 호출 하는 함수를 포함 하는 DLL의 위치입니다. Windows 시스템 디렉터리에 있는 파일의 경로를 지정할 필요가 없습니다. 두 번째 매개 변수는 Windows API에서 함수 이름을 지정 하는 명명 된 인수입니다. 이 예는 `DllImport` 특성에 대 한 호출을 강제로 `MoveFile` 전달할 `MoveFileW` KERNEL32에서. DLL입니다. 합니다 `MoveFileW` 메서드는 경로에서 파일을 복사 `src` 경로에 `dst`입니다.  
  
     [!code-vb[VbVbalrInterop#17](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_7.vb)]  
  
9. 코드를 추가 하는 `Button2_Click` 이벤트 처리기 함수를 호출 합니다.  
  
     [!code-vb[VbVbalrInterop#18](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_8.vb)]  
  
10. Test.txt 라는 파일을 만들고 하드 드라이브 C:\Tmp 디렉터리에 배치 합니다. 필요한 경우 Tmp 디렉터리를 만듭니다.  
  
11. F5 키를 눌러 응용 프로그램을 시작합니다. 기본 폼이 나타납니다.  
  
12. 클릭 **Button2**합니다. 파일을 이동할 수 있는 경우 "파일을 성공적으로 이동" 메시지가 표시 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Runtime.InteropServices.DllImportAttribute>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [Declare 문](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [자동](../../../visual-basic/language-reference/modifiers/auto.md)  
 [Alias](../../../visual-basic/language-reference/statements/alias-clause.md)  
 [COM Interop](../../../visual-basic/programming-guide/com-interop/index.md)  
 [관리 코드에서 프로토타입 만들기](../../../framework/interop/creating-prototypes-in-managed-code.md)  
 [콜백 메서드로 대리자 마샬링](../../../framework/interop/marshaling-a-delegate-as-a-callback-method.md)
