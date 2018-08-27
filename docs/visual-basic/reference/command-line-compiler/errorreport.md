---
title: -errorreport
ms.date: 08/14/2018
helpviewer_keywords:
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d093b8ce4413a375e79eec239be37e83ac674d05
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2018
ms.locfileid: "42929945"
---
# <a name="-errorreport"></a>-errorreport

Visual Basic 컴파일러에서 내부 컴파일러 오류를 보고 하는 방법을 지정 합니다.

## <a name="syntax"></a>구문

```
-errorreport:{ prompt | queue | send | none }
```

## <a name="remarks"></a>설명

이 옵션에는 microsoft Visual Basic 팀에 Visual Basic 내부 컴파일러 오류 (ICE)를 보고 하는 편리한 방법을 제공 합니다. 기본적으로 컴파일러는 Microsoft에 없는 정보를 보냅니다. 그러나 내부 컴파일러 오류가 발생 수행을 하는 경우이 옵션 Microsoft로 오류를 보고 수 있습니다. 이 정보는 Microsoft 엔지니어가 원인을 파악 하는 데 도움이 되며 Visual Basic의 다음 릴리스를 개선 하는 데 도움이 될 수 있습니다.

보고서를 보내는 사용자의 능력 컴퓨터 및 사용자 정책 권한에 따라 달라 집니다.

다음 표에서 요약의 효과 `-errorreport` 옵션입니다.

|옵션|동작|
|---|---|
|`prompt`|내부 컴파일러 오류가 발생 하는 경우 대화 상자가 나타난 컴파일러에서 수집한 정확한 데이터를 볼 수 있도록 합니다. 오류 보고서에 대 한 중요 한 정보가 있는지 확인 하 고 Microsoft로 보낼지 여부를 결정을 내릴 수 있습니다. 보내기로 컴퓨터 및 사용자 정책 설정에서 허용 하 고 컴파일러는 데이터를 Microsoft로 보냅니다.|
|`queue`|오류 보고서를 큐에 넣습니다. 관리자 권한으로 로그인 하는 경우에 기록 된 마지막 시간 이후 발생 한 모든 오류를 보고할 수 있습니다 (하지 묻는 3 일 마다 한 번에 오류에 대 한 보고서를 보내도록). 이 기본 동작은 때는 `-errorreport` 옵션이 지정 되지 않은 합니다.|
|`send`|내부 컴파일러 오류가 발생 하 고 컴퓨터 및 사용자 정책 설정에서 허용 하는 경우 컴파일러는 Microsoft로 데이터를 보냅니다.<br /><br /> 옵션 `-errorreport:send` 하 여 보고를 사용 하는 경우 Microsoft로 오류 정보를 자동으로 보낼 시도 합니다 [Windows 오류 보고](/windows/desktop/wer/windows-error-reporting) 시스템 설정 합니다. |
|`none`|내부 컴파일러 오류가 발생 하는 경우 되거나 되지 않습니다 수 수집 Microsoft로 전송 합니다.|

컴파일러는 일반적으로 일부 소스 코드를 포함 하는 오류 시 스택을 포함 하는 데이터를 보냅니다. 하는 경우 `-errorreport` 사용 되는 [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) 옵션을 전체 소스 파일이 전송 됩니다.

이 옵션은 사용 하 여 가장 적합 합니다 [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) 옵션을 자세히 하기 위해 Microsoft 엔지니어가 오류를 쉽게 재현할 수 있기 때문입니다.

> [!NOTE]
> `-errorreport` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 있는 명령줄에서 컴파일할 경우에 사용할 수 있는 것입니다.

## <a name="example"></a>예

다음 코드를 컴파일하려고 시도 `T2.vb`, 한 컴파일러에 내부 컴파일러 오류가 발생 하는 경우 Microsoft로 오류 보고서를 보낼 것인지 묻습니다.

```
vbc -errorreport:prompt t2.vb
```

## <a name="see-also"></a>참고자료

- [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
- [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)
