---
title: '어셈블리를 생성할 수 없습니다: &lt;오류 메시지&gt;'
ms.date: 07/20/2015
f1_keywords:
- vbc30145
- bc30145
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
ms.openlocfilehash: 8f497069088ad30a3be58d02caa0a32f7f1b21b7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="unable-to-emit-assembly-lterror-messagegt"></a>어셈블리를 생성할 수 없습니다: &lt;오류 메시지&gt;
Visual Basic 컴파일러 링커 어셈블리 만들기의 내보내기 단계에서 오류가 보고 어셈블리 링커 (Al.exe, Alink 라고도 함)는 매니페스트를 사용해 어셈블리를 생성 하려면를 호출 합니다.  
  
 **오류 ID:** BC30145  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  따옴표 붙은 오류 메시지를 검사 하 고 항목을 검토 [Al.exe](../../../framework/tools/al-exe-assembly-linker.md)합니다. 추가 설명과 권장 사항을 합니다.  
  
2.  어셈블리 중 하나를 사용 하 여 수동으로 서명을 시도 [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) 또는 [Sn.exe (강력한 이름 도구)](../../../framework/tools/sn-exe-strong-name-tool.md)합니다.  
  
3.  오류가 계속 발생하면 해당 상황에 대한 정보를 수집하여 Microsoft 기술 지원 서비스에 알립니다.  
  
### <a name="to-sign-the-assembly-manually"></a>어셈블리에 수동으로 서명하려면  
  
1.  [Sn.exe (강력한 이름 도구)]를 사용 하 여[Sn.exe (강력한 이름 도구)](../../../framework/tools/sn-exe-strong-name-tool.md)) 공개/개인 키 쌍 파일을 만듭니다.  
  
     이 파일의 확장명은 .snk입니다.  
  
2.  프로젝트에서 오류를 생성하는 COM 참조를 삭제합니다.  
  
3.  Windows에서 **시작** 메뉴에서 **프로그램**, 가리킨 **Microsoft Visual Studio 2008**, 가리킨 **Visual Studio Tools**, 및 클릭 **Visual Studio 2008 명령 프롬프트**합니다.  
  
4.  어셈블리 래퍼를 배치할 디렉터리로 이동합니다.  
  
5.  다음 코드를 입력합니다.  
  
    ```  
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>  
    ```  
  
     입력할 수 있는 코드의 예는 다음과 같습니다.  
  
    ```  
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"  
    ```  
  
     경로나 파일에 공백이 있으면 큰따옴표(")를 사용합니다.  
  
6.  Visual Studio에서 방금 만든 파일에 대 한.NET 어셈블리 참조를 추가 합니다.  
  
## <a name="see-also"></a>참고 항목  
 
 [Al.exe](../../../framework/tools/al-exe-assembly-linker.md)합니다.  
 [Sn.exe (강력한 이름 도구)] [Sn.exe (강력한 이름 도구)](../../../framework/tools/sn-exe-strong-name-tool.md))  
 [방법: 공개/개인 키 쌍 만들기](../../../framework/app-domains/how-to-create-a-public-private-key-pair.md)  
 [의견 보내기](/visualstudio/ide/talk-to-us)
