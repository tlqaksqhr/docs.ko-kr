---
title: "Constants and Enumerations (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "enumerations [Visual Basic]"
  - "constants"
  - "constants, list of"
ms.assetid: 309c0ad5-83e4-4f96-99ea-83cd95107417
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Constants and Enumerations (Visual Basic)
[!INCLUDE[vs2017banner](../../csharp/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서는 개발자용으로 미리 정의된 상수와 열거형이 여러 가지가 제공됩니다.  상수는 응용 프로그램을 실행하는 동안 일정하게 유지되는 값을 저장하며,  열거형은 관련 상수 집합을 사용하고 상수 값을 이름과 연결하는 편리한 방법을 제공합니다.  
  
## 상수  
  
### 조건부 컴파일 상수  
 다음 표에서는 조건부 컴파일에 사용할 수 있는 미리 정의된 상수를 보여 줍니다.  
  
|||  
|-|-|  
|**상수**|**설명**|  
|`CONFIG`|**구성 관리자**에 있는 **활성 솔루션 구성** 상자의 현재 설정에 해당하는 문자열입니다.|  
|`DEBUG`|**프로젝트 속성** 대화 상자에서 설정할 수 있는 `Boolean` 값입니다.  기본적으로 프로젝트의 디버그 구성은 `DEBUG`를 정의합니다.  `DEBUG`를 정의하면 <xref:System.Diagnostics.Debug> 클래스 메서드의 결과가 **출력** 창에 표시됩니다.  이 상수를 정의하지 않으면 <xref:System.Diagnostics.Debug> 클래스 메서드가 컴파일되지 않으므로 디버그 결과가 표시되지 않습니다.|  
|`TARGET`|프로젝트의 출력 형식 또는 **\/target** 명령줄 옵션의 설정을 나타내는 문자열입니다.  `TARGET`의 가능한 값은 다음과 같습니다.<br /><br /> -   "winexe" \- Windows 응용 프로그램의 경우<br />-   "exe" \- 콘솔 응용 프로그램의 경우<br />-   "library" \- 클래스 라이브러리의 경우<br />-   "module" \- 모듈의 경우<br />-   **\/target** 옵션은 [!INCLUDE[vsprvs](../../csharp/includes/vsprvs_md.md)] 통합 개발 환경에 설정할 수 있습니다.  자세한 내용은 [\/target](../../visual-basic/reference/command-line-compiler/target.md)을 참조하십시오.|  
|`TRACE`|**프로젝트 속성** 대화 상자에서 설정할 수 있는 `Boolean` 값입니다.  기본적으로 프로젝트의 모든 구성은 `TRACE`를 정의합니다.  `TRACE`를 정의하면 <xref:System.Diagnostics.Trace> 클래스 메서드의 결과가 **출력** 창에 표시됩니다.  이 상수를 정의하지 않으면 <xref:System.Diagnostics.Trace> 클래스 메서드가 컴파일되지 않으므로 `Trace` 결과가 생성되지 않습니다.|  
|`VBC_VER`|[!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 버전을 나타내는 *major*.*minor* 형식의 숫자입니다.  [!INCLUDE[vbprvblong](../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)]의 버전 번호는 8.0입니다.|  
  
### 출력 및 표시 상수  
 출력 및 표시 함수를 호출하는 경우 실제 값 대신 코드에 다음과 같은 상수를 사용할 수 있습니다.  
  
|||  
|-|-|  
|**상수**|**설명**|  
|`vbCrLf`|캐리지 리턴\/줄 바꿈 문자 조합|  
|`vbCr`|캐리지 리턴 문자|  
|`vbLf`|줄 바꿈 문자|  
|`vbNewLine`|줄 바꿈 문자|  
|`vbNullChar`|Null 문자|  
|`vbNullString`|길이가 0인 문자열\(""\)과는 다르며 외부 프로시저를 호출하는 데 사용됩니다.|  
|`vbObjectError`|오류 번호.  사용자 정의 오류 번호는 이 값보다 커야 합니다.  예를 들면 다음과 같습니다.<br /><br /> `Err.Raise(Number) = vbObjectError + 1000`|  
|`vbTab`|탭 문자|  
|`vbBack`|백스페이스 문자|  
|`vbFormFeed`|Microsoft Windows에서는 사용되지 않습니다.|  
|`vbVerticalTab`|Microsoft Windows에서는 유용하지 않습니다.|  
  
## 열거형  
 다음 표에서는 [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서 제공하는 열거형을 보여 줍니다.  
  
|||  
|-|-|  
|열거형|설명|  
|<xref:Microsoft.VisualBasic.AppWinStyle>|<xref:Microsoft.VisualBasic.Interaction.Shell%2A> 함수를 호출할 때 호출된 프로그램에 사용할 창 스타일을 나타냅니다.|  
|<xref:Microsoft.VisualBasic.AudioPlayMode>|오디오 메서드를 호출할 때 소리가 재생되는 방식을 나타냅니다.|  
|<xref:Microsoft.VisualBasic.ApplicationServices.BuiltInRole>|<xref:Microsoft.VisualBasic.ApplicationServices.User.IsInRole%2A> 메서드를 호출할 때 확인할 역할 유형을 나타냅니다.|  
|<xref:Microsoft.VisualBasic.CallType>|<xref:Microsoft.VisualBasic.Interaction.CallByName%2A> 함수를 호출할 때 호출되는 프로시저 형식을 나타냅니다.|  
|<xref:Microsoft.VisualBasic.CompareMethod>|비교 함수를 호출할 때 문자열이 비교되는 방법을 나타냅니다.|  
|<xref:Microsoft.VisualBasic.DateFormat>|<xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A> 함수를 호출할 때 날짜가 표시되는 방법을 나타냅니다.|  
|<xref:Microsoft.VisualBasic.DateInterval>|날짜 관련 함수를 호출할 때 날짜 간격을 설정하고 서식을 지정하는 방법을 나타냅니다.|  
|<xref:Microsoft.VisualBasic.FileIO.DeleteDirectoryOption>|삭제될 디렉터리에 파일이나 디렉터리가 포함된 경우 수행해야 하는 작업을 지정합니다.|  
|<xref:Microsoft.VisualBasic.DueDate>|금융 메서드를 호출할 때 지불 만기일을 나타냅니다.|  
|<xref:Microsoft.VisualBasic.FileIO.FieldType>|텍스트 필드가 구분되어 있는지 또는 고정 폭인지 여부를 나타냅니다.|  
|<xref:Microsoft.VisualBasic.FileAttribute>|파일 액세스 함수를 호출할 때 사용할 파일 특성을 나타냅니다.|  
|<xref:Microsoft.VisualBasic.FirstDayOfWeek>|날짜 관련 함수를 호출할 때 사용할 주의 첫째 요일을 나타냅니다.|  
|<xref:Microsoft.VisualBasic.FirstWeekOfYear>|날짜 관련 함수를 호출할 때 사용할 연도의 첫째 주를 나타냅니다.|  
|<xref:Microsoft.VisualBasic.MsgBoxResult>|메시지 상자에서 눌러진 단추\(<xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> 함수에서 반환\)를 나타냅니다.|  
|<xref:Microsoft.VisualBasic.MsgBoxStyle>|<xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> 함수를 호출할 때 표시할 단추를 나타냅니다.|  
|<xref:Microsoft.VisualBasic.OpenAccess>|파일 액세스 함수를 호출할 때 파일을 여는 방법을 나타냅니다.|  
|<xref:Microsoft.VisualBasic.OpenMode>|파일 액세스 함수를 호출할 때 파일을 여는 방법을 나타냅니다.|  
|<xref:Microsoft.VisualBasic.OpenShare>|파일 액세스 함수를 호출할 때 파일을 여는 방법을 나타냅니다.|  
|<xref:Microsoft.VisualBasic.FileIO.RecycleOption>|파일을 영구적으로 삭제할지 아니면 휴지통에 넣을지 지정합니다.|  
|<xref:Microsoft.VisualBasic.FileIO.SearchOption>|모든 디렉터리를 검색할지 최상위 디렉터리만 검색할지 지정합니다.|  
|<xref:Microsoft.VisualBasic.TriState>|숫자 형식 지정 함수를 호출할 때 기본값을 사용할지 여부 또는 `Boolean` 값을 나타냅니다.|  
|<xref:Microsoft.VisualBasic.FileIO.UICancelOption>|작업 중 사용자가 **취소**를 클릭할 경우 수행할 작업을 지정합니다.|  
|<xref:Microsoft.VisualBasic.FileIO.UIOption>|파일이나 디렉터리를 복사, 삭제 또는 이동할 때 진행률 대화 상자의 표시 여부를 지정합니다.|  
|<xref:Microsoft.VisualBasic.VariantType>|variant 개체의 형식을 나타내며 <xref:Microsoft.VisualBasic.Information.VarType%2A> 함수에서 반환됩니다.|  
|<xref:Microsoft.VisualBasic.VbStrConv>|<xref:Microsoft.VisualBasic.Strings.StrConv%2A> 함수를 호출할 때 수행할 변환 형식을 나타냅니다.|  
  
## 참고 항목  
 [Visual Basic Language Reference](../../visual-basic/language-reference/index.md)   
 [Visual Basic](../../visual-basic/index.md)   
 [Constants Overview](../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)   
 [Enumerations Overview](../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)