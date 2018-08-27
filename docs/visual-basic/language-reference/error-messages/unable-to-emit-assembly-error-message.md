---
title: 어셈블리를 생성할 수 없습니다. <error message>
ms.date: 08/14/2018
f1_keywords:
- vbc30145
- bc30145
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
ms.openlocfilehash: 404a8255adcdc414a40b40395ada1c90c1078325
ms.sourcegitcommit: a1e35d4e94edab384a63406c0a5438306873031b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2018
ms.locfileid: "42754115"
---
# <a name="unable-to-emit-assembly-error-message"></a>어셈블리를 생성할 수 없습니다: \<오류 메시지 >

Visual Basic 컴파일러에서 어셈블리 링커 호출 (*Al.exe*, Alink 라고도) 매니페스트와 링커를 사용 하 여 어셈블리를 생성할 어셈블리를 만들 때의 내보내기 단계에서 오류를 보고 합니다.

**오류 ID:** BC30145

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

1. 따옴표 붙은 오류 메시지를 확인 하 고 항목을 참조 하십시오 [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) 추가 설명과 권장 사항을 대 한 합니다.

2. 어셈블리 중 하나를 사용 하 여 수동으로 로그인을 시도 합니다 [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) 또는 [Sn.exe (강력한 이름 도구)](../../../framework/tools/sn-exe-strong-name-tool.md)합니다.

3. 오류가 계속 발생하면 해당 상황에 대한 정보를 수집하여 Microsoft 기술 지원 서비스에 알립니다.

### <a name="to-sign-the-assembly-manually"></a>어셈블리에 수동으로 서명하려면

1. 사용 된 [Sn.exe (강력한 이름 도구)](../../../framework/tools/sn-exe-strong-name-tool.md)) 공개/개인 키 쌍 파일을 만듭니다.

   이 파일에는 *.snk* 확장 합니다.

2. 프로젝트에서 오류를 생성하는 COM 참조를 삭제합니다.

3. 엽니다는 [Visual Studio 용 개발자 명령 프롬프트](../../../framework/tools/developer-command-prompt-for-vs.md)합니다.

   Windows 10에서 입력 **개발자 명령 프롬프트** 작업 표시줄에서 검색 상자에 있습니다. 그런 다음 선택 **VS 2017 용 개발자 명령 프롬프트** 결과 목록에서.

4. 어셈블리 래퍼를 배치 하려는 디렉터리로 디렉터리를 변경 합니다.

5. 다음 명령을 입력합니다.

    ```cmd
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>
    ```

   입력할 수 있는 실제 명령의 예로:

    ```cmd
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"
    ```

   > [!TIP]
   > 경로 또는 파일에 공백이 있으면 큰따옴표를 사용 합니다.

6. Visual Studio의 방금 만든 파일에 대 한.NET 어셈블리 참조를 추가 합니다.

## <a name="see-also"></a>참고자료

- [Al.exe](../../../framework/tools/al-exe-assembly-linker.md)합니다.
- [Sn.exe (강력한 이름 도구)] [Sn.exe (강력한 이름 도구)](../../../framework/tools/sn-exe-strong-name-tool.md))
- [방법: 공개/개인 키 쌍 만들기](../../../framework/app-domains/how-to-create-a-public-private-key-pair.md)
- [의견 보내기](/visualstudio/ide/talk-to-us)