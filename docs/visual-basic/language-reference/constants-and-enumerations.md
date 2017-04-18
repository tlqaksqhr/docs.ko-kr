---
title: "상수 및 열거형 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- enumerations [Visual Basic]
- constants
- constants, list of
ms.assetid: 309c0ad5-83e4-4f96-99ea-83cd95107417
caps.latest.revision: 18
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
ms.openlocfilehash: e37ef2e3c51e96e85cb214054195016e69d52382
ms.lasthandoff: 03/13/2017

---
# <a name="constants-and-enumerations-visual-basic"></a>상수 및 열거형(Visual Basic)
[!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]다양 한 미리 정의 된 상수와 개발자에 대 한 열거형을 제공합니다. 상수는 응용 프로그램의 실행 되는 동안 일정 하 게 유지 하는 값을 저장 합니다. 열거형에는 관련된 상수 집합으로 작업 하 고 이름의 상수 값을 연결 하는 편리한 방법을 제공 합니다.  
  
## <a name="constants"></a>상수  
  
### <a name="conditional-compilation-constants"></a>조건부 컴파일 상수  
 다음 표에서 조건부 컴파일에 사용할 수 있는 미리 정의 된 상수를 나열합니다.  
  
|**상수**|**설명**|  
|---|---|  
|`CONFIG`|현재 설정에 해당 하는 문자열은 **활성 솔루션 구성** 상자에 **Configuration Manager**합니다.|  
|`DEBUG`|A `Boolean` 에서 설정할 수 있는 값은 **프로젝트 속성** 대화 상자입니다. 기본적으로 프로젝트의 디버그 구성을 정의 `DEBUG`합니다. 때 `DEBUG` 정의 된 <xref:System.Diagnostics.Debug>클래스 메서드의 결과가 **출력** 창.</xref:System.Diagnostics.Debug> 정의 되지 않은 경우 <xref:System.Diagnostics.Debug>클래스 메서드가 컴파일되지 않으므로 및 디버그 출력이 생성 되지 않습니다.</xref:System.Diagnostics.Debug>|  
|`TARGET`|프로젝트 또는 명령줄의 설정에 대 한 출력 형식을 나타내는 문자열 **/대상** 옵션입니다. 가능한 값 `TARGET` 됩니다.<br /><br /> -Windows 응용 프로그램에 대 한 "winexe"입니다.<br />-콘솔 응용 프로그램에 대 한 "exe"입니다.<br />-클래스 라이브러리에 대 한 "library"입니다.<br />-"한 모듈에 대 한" 모듈입니다.<br />- **/대상** 옵션에서 설정할 수 있습니다는 [!INCLUDE[vsprvs](../../csharp/includes/vsprvs_md.md)] 통합된 개발 환경입니다. 자세한 내용은 참조 [/target (Visual Basic)](../../visual-basic/reference/command-line-compiler/target.md)합니다.|  
|`TRACE`|A `Boolean` 에서 설정할 수 있는 값은 **프로젝트 속성** 대화 상자입니다. 기본적으로 프로젝트에 대 한 모든 구성을 정의 `TRACE`합니다. 때 `TRACE` 정의 된 <xref:System.Diagnostics.Trace>클래스 메서드의 결과가 **출력** 창.</xref:System.Diagnostics.Trace> 정의 되지 않은 경우 <xref:System.Diagnostics.Trace>클래스 메서드가 컴파일되지 않으므로 및 no `Trace` 출력이 생성 됩니다.</xref:System.Diagnostics.Trace>|  
|`VBC_VER`|나타내는 숫자는 [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 버전에서 *주요*.* 보조* 형식입니다. 버전 번호를 [!INCLUDE[vbprvblong](../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] 8.0 됩니다.|  
  
### <a name="print-and-display-constants"></a>인쇄 및 표시 상수  
 인쇄를 호출 하 고 함수를 표시 하는 경우에 실제 값 대신 코드에서 다음 상수를 사용할 수 있습니다.  
  
|**상수**|**설명**|  
|---|---|  
|`vbCrLf`|캐리지 리턴/줄 바꿈 문자 조합입니다.|  
|`vbCr`|캐리지 리턴 문자입니다.|  
|`vbLf`|줄 바꿈 문자입니다.|  
|`vbNewLine`|줄 바꿈 문자입니다.|  
|`vbNullChar`|Null 문자입니다.|  
|`vbNullString`|동일 하지는 길이가&0; 인 문자열 (""); 외부 프로시저를 호출 하는 데 사용 합니다.|  
|`vbObjectError`|오류 번호 사용자 정의 오류 번호는이 값 보다 커야 합니다. 예:<br /><br /> `Err.Raise(Number) = vbObjectError + 1000`|  
|`vbTab`|탭 문자입니다.|  
|`vbBack`|백스페이스 문자입니다.|  
|`vbFormFeed`|Microsoft Windows에서 사용 되지 않습니다.|  
|`vbVerticalTab`|Microsoft Windows에서 유용 하지 않습니다.|  
  
## <a name="enumerations"></a>열거형  
 다음 표에 및에서 제공 하는 열거형 [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]합니다.  
  
|열거형|설명|  
|---|---|  
|<xref:Microsoft.VisualBasic.AppWinStyle></xref:Microsoft.VisualBasic.AppWinStyle>|창 스타일을 호출할 때 호출된 프로그램에 사용할 나타냅니다는 <xref:Microsoft.VisualBasic.Interaction.Shell%2A>함수.</xref:Microsoft.VisualBasic.Interaction.Shell%2A>|  
|<xref:Microsoft.VisualBasic.AudioPlayMode></xref:Microsoft.VisualBasic.AudioPlayMode>|오디오 메서드를 호출할 때 소리를 재생 하는 방법을 나타냅니다.|  
|<xref:Microsoft.VisualBasic.ApplicationServices.BuiltInRole></xref:Microsoft.VisualBasic.ApplicationServices.BuiltInRole>|호출할 때 확인할 역할의 유형을 나타냅니다는 <xref:Microsoft.VisualBasic.ApplicationServices.User.IsInRole%2A>메서드.</xref:Microsoft.VisualBasic.ApplicationServices.User.IsInRole%2A>|  
|<xref:Microsoft.VisualBasic.CallType></xref:Microsoft.VisualBasic.CallType>|호출할 때 호출 되는 프로시저의 유형을 나타냅니다는 <xref:Microsoft.VisualBasic.Interaction.CallByName%2A>함수.</xref:Microsoft.VisualBasic.Interaction.CallByName%2A>|  
|<xref:Microsoft.VisualBasic.CompareMethod></xref:Microsoft.VisualBasic.CompareMethod>|비교 함수를 호출할 때 문자열을 비교 하는 방법을 나타냅니다.|  
|<xref:Microsoft.VisualBasic.DateFormat></xref:Microsoft.VisualBasic.DateFormat>|날짜를 표시 하는 방법을 나타내는 호출 하는 경우는 <xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A>함수.</xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A>|  
|<xref:Microsoft.VisualBasic.DateInterval></xref:Microsoft.VisualBasic.DateInterval>|날짜 관련 함수를 호출할 때 날짜 간격을 결정하고 형식을 지정하는 방법을 나타냅니다.|  
|<xref:Microsoft.VisualBasic.FileIO.DeleteDirectoryOption></xref:Microsoft.VisualBasic.FileIO.DeleteDirectoryOption>|수행 해야 할 파일이 나 디렉터리를 삭제 해야 하는 디렉터리를 포함 하는 경우를 지정 합니다.|  
|<xref:Microsoft.VisualBasic.DueDate></xref:Microsoft.VisualBasic.DueDate>|지불 하는 시점을 나타내는 재무 메서드를 호출할 때입니다.|  
|<xref:Microsoft.VisualBasic.FileIO.FieldType></xref:Microsoft.VisualBasic.FileIO.FieldType>|텍스트 필드가 구분 되어 있는지 여부 또는 고정 너비를 나타냅니다.|  
|<xref:Microsoft.VisualBasic.FileAttribute></xref:Microsoft.VisualBasic.FileAttribute>|파일 액세스 함수를 호출할 때 사용 하 여 파일 특성을 나타냅니다.|  
|<xref:Microsoft.VisualBasic.FirstDayOfWeek></xref:Microsoft.VisualBasic.FirstDayOfWeek>|날짜 관련 함수를 호출할 때 사용 하 여 첫 번째 요일을 나타냅니다.|  
|<xref:Microsoft.VisualBasic.FirstWeekOfYear></xref:Microsoft.VisualBasic.FirstWeekOfYear>|날짜 관련 함수를 호출할 때 사용 하는 연도의 첫째 주를 나타냅니다.|  
|<xref:Microsoft.VisualBasic.MsgBoxResult></xref:Microsoft.VisualBasic.MsgBoxResult>|반환 되는 메시지 상자에서 단추를 눌렀는지 나타냅니다는 <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>함수.</xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>|  
|<xref:Microsoft.VisualBasic.MsgBoxStyle></xref:Microsoft.VisualBasic.MsgBoxStyle>|호출할 때 표시할 단추를 나타내는 <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>함수.</xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>|  
|<xref:Microsoft.VisualBasic.OpenAccess></xref:Microsoft.VisualBasic.OpenAccess>|파일 액세스 함수를 호출할 때 파일을 여는 방법을 나타냅니다.|  
|<xref:Microsoft.VisualBasic.OpenMode></xref:Microsoft.VisualBasic.OpenMode>|파일 액세스 함수를 호출할 때 파일을 여는 방법을 나타냅니다.|  
|<xref:Microsoft.VisualBasic.OpenShare></xref:Microsoft.VisualBasic.OpenShare>|파일 액세스 함수를 호출할 때 파일을 여는 방법을 나타냅니다.|  
|<xref:Microsoft.VisualBasic.FileIO.RecycleOption></xref:Microsoft.VisualBasic.FileIO.RecycleOption>|파일을 영구적으로 삭제할지 아니면 휴지통에 배치를 지정 합니다.|  
|<xref:Microsoft.VisualBasic.FileIO.SearchOption></xref:Microsoft.VisualBasic.FileIO.SearchOption>|모든 디렉터리를 검색할지 여부를 지정 하거나 최상위 디렉터리만 있습니다.|  
|<xref:Microsoft.VisualBasic.TriState></xref:Microsoft.VisualBasic.TriState>|나타냅니다는 `Boolean` 값 이나 숫자 형식 지정 함수를 호출할 때 기본값을 사용할지 여부입니다.|  
|<xref:Microsoft.VisualBasic.FileIO.UICancelOption></xref:Microsoft.VisualBasic.FileIO.UICancelOption>|지정 해야 사용자가 클릭할 경우 수행할 작업 **취소** 작업 중입니다.|  
|<xref:Microsoft.VisualBasic.FileIO.UIOption></xref:Microsoft.VisualBasic.FileIO.UIOption>|복사, 삭제 또는 파일이 나 디렉터리를 이동할 때 진행률 대화 상자를 표시할 것인지 여부를 지정 합니다.|  
|<xref:Microsoft.VisualBasic.VariantType></xref:Microsoft.VisualBasic.VariantType>|반환 하는 variant 개체의 유형을 나타냅니다는 <xref:Microsoft.VisualBasic.Information.VarType%2A>함수.</xref:Microsoft.VisualBasic.Information.VarType%2A>|  
|<xref:Microsoft.VisualBasic.VbStrConv></xref:Microsoft.VisualBasic.VbStrConv>|호출할 때 수행 하는 변환의 형식을 나타냅니다는 <xref:Microsoft.VisualBasic.Strings.StrConv%2A>함수.</xref:Microsoft.VisualBasic.Strings.StrConv%2A>|  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 언어 참조](../../visual-basic/language-reference/index.md)   
 [Visual Basic](../../visual-basic/index.md)   
 [상수 개요](../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)   
 [열거형 개요](../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
