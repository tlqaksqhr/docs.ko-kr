---
title: '어셈블리 매니페스트를 만드는 동안 오류 발생: &lt;오류 메시지&gt;'
ms.date: 07/20/2015
f1_keywords:
- bc30140
- vbc30140
helpviewer_keywords:
- BC30140
ms.assetid: 1beb5aa0-7b79-4c85-946b-5c2d0a41d1d2
ms.openlocfilehash: b3ea5b502abd318c34d957bf7f540602c53c9e6b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588303"
---
# <a name="error-creating-assembly-manifest-lterror-messagegt"></a>어셈블리 매니페스트를 만드는 동안 오류 발생: &lt;오류 메시지&gt;
Visual Basic 컴파일러는 매니페스트를 사용해 어셈블리를 생성 하는 어셈블리 링커 (Al.exe, Alink 라고도 함)를 호출 합니다. 링커가 어셈블리 만들기의 내보내기 전 단계에서 오류를 보고했습니다.  
  
 지정한 키 파일 또는 키 컨테이너에 문제가 있으면 이러한 현상이 발생할 수 있습니다. 어셈블리에 완전히 서명을 하려면 공개 키와 개인 키에 대한 정보가 포함된 유효한 키 파일을 제공해야 합니다. 어셈블리 서명을 연기하려면 **서명만 연기** 확인란을 선택하고 공개 키에 대한 정보가 포함된 유효한 키 파일을 제공해야 합니다. 어셈블리 서명을 연기할 때 개인 키는 필요하지 않습니다. 자세한 내용은 [방법: 강력한 이름으로 어셈블리 서명](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)을 참조하세요.  
  
 **오류 ID:** BC30140  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  따옴표 붙은 오류 메시지를 검사 하 고 항목을 검토 [Al.exe](../../../framework/tools/al-exe-assembly-linker.md)합니다. 오류 AL1019 추가 설명과 권장 사항을  
  
2.  오류가 계속 발생하면 해당 상황에 대한 정보를 수집하여 Microsoft 기술 지원 서비스에 알립니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 강력한 이름으로 어셈블리 서명](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)  
 [프로젝트 디자이너, 서명 페이지](/visualstudio/ide/reference/signing-page-project-designer)  
 [Al.exe](../../../framework/tools/al-exe-assembly-linker.md)합니다.  
 [의견 보내기](/visualstudio/ide/talk-to-us)
