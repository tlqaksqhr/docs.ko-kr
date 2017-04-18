---
title: "/delaysign | Microsoft 문서"
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
- delaysign compiler option [Visual Basic]
- /delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
caps.latest.revision: 19
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
ms.openlocfilehash: 59d4ec227286c20b2b4ecf749a91f0c4ee8d25ca
ms.lasthandoff: 03/13/2017

---
# <a name="delaysign"></a>T:System.Reflection.AssemblyDelaySignAttribute
어셈블리를 완전히 서명할지, 아니면 부분적으로 서명할지를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/delaysign[+ | -]  
```  
  
## <a name="arguments"></a>인수  
 `+` &#124; `-`  
 선택적 요소. 어셈블리에 완전히 서명하려면 `/delaysign-`를 사용하고 사용 하 여 `/delaysign+` 부호 있는 해시에 대 한 어셈블리 및 예약 공간에 공개 키를 저장 하려는 경우. 기본값은 `/delaysign-`입니다.  
  
## <a name="remarks"></a>주의  
 `/delaysign` 와 사용 하지 않는 경우 옵션은 효과가 없습니다 [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) 또는 [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)합니다.  
  
 완전히 서명 된 어셈블리를 요청 하는 경우 컴파일러는 매니페스트 (어셈블리 메타 데이터)를 포함 하 고 개인 키로 해당 해시에 서명 하는 파일을 해시 합니다. 결과로 생성되는 디지털 서명은 매니페스트가 포함된 파일에 저장됩니다. 어셈블리 서명이 연기 되 면 컴파일러 계산 및 나중에 서명을 추가할 수 있도록 파일에 서명을 하지만 예약 공간을 저장 하지 않습니다.  
  
 사용 하 여 예를 들어 `/delaysign+`, 개발자는 조직에서 테스터가 어셈블리를 전역 어셈블리 캐시에 등록 하 고 사용할 수 있는 어셈블리의 서명 되지 않은 테스트 버전을 배포할 수 있습니다. 어셈블리 작업이 완료 되 면 회사의 개인 키를 담당 하는 사용자 어셈블리에 완전히 서명할 수 있습니다. 이 작업의 공개, 모든 개발자 들이 어셈블리에서 작동 하면서 회사의 개인 키를 보호 합니다.  
  
 참조 [Creating and using strong-named Assemblies](https://msdn.microsoft.com/library/xwb8f617) 어셈블리 서명에 대 한 자세한 내용은 합니다.  
  
### <a name="to-set-delaysign-in-the-visual-studio-integrated-development-environment"></a>Visual Studio에서 /delaysign을 설정 하려면 통합 개발 환경  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택합니다. 에 **프로젝트** 메뉴를 클릭 하 여 **속성**합니다. 자세한 내용은 [프로젝트 디자이너 소개](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하세요.  
  
2.  클릭 하 고 **서명** 탭 합니다.  
  
3.  값을 설정 된 **서명만 연기** 상자입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)   
 [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
