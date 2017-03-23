---
title: "/rootnamespace | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /rootnamespace
- rootnamespace
dev_langs:
- VB
helpviewer_keywords:
- /rootnamespace compiler option [Visual Basic]
- -rootnamespace compiler option [Visual Basic]
- rootnamespace compiler option [Visual Basic]
ms.assetid: e9245edf-6bef-420d-a7c7-324117752783
caps.latest.revision: 13
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 7b261efeb829a6c0b035d7364c63074412a91c7f
ms.lasthandoff: 03/13/2017

---
# <a name="rootnamespace"></a>/rootnamespace
모든 형식 선언에 대한 네임스페이스를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/rootnamespace:namespace  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`namespace`|현재 프로젝트에 대 한 모든 형식 선언을 포함할를 네임 스페이스의 이름입니다.|  
  
## <a name="remarks"></a>설명  
 사용 하 여 Visual Studio 통합된 개발 환경에서 만든 프로젝트를 컴파일하려면 Visual Studio 실행 파일 (Devenv.exe)를 사용 하는 경우 `/rootnamespace` 의 값을 지정 하는 <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A>속성.</xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> 참조 [Devenv 명령줄 스위치](https://docs.microsoft.com/visualstudio/ide/reference/devenv-command-line-switches) 에 대 한 자세한 내용은 합니다.  
  
 공용 언어 런타임 MSIL 디스어셈블러를 사용 하 여 (I`ldasm.exe`) 출력 파일에 네임 스페이스 이름을 볼 수 있습니다.  
  
|Visual Studio에서 /rootnamespace를 설정 하려면 통합 개발 환경|  
|---|  
|1.  **솔루션 탐색기**에서 프로젝트를 선택합니다. 에 **프로젝트** 메뉴를 클릭 하 여 **속성**합니다. 자세한 내용은 [프로젝트 디자이너 소개](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하세요.<br />2.  **응용 프로그램** 탭을 클릭합니다.<br />3.  값을 수정 된 **루트 Namespace** 상자입니다.|  
  
## <a name="example"></a>예제  
 다음 코드에서는 `In.vb` 네임 스페이스의 모든 형식 선언을 포함 하 고 `mynamespace`합니다.  
  
```  
vbc /rootnamespace:mynamespace in.vb  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Ildasm.exe (IL 디스어셈블러)](https://msdn.microsoft.com/library/f7dy01k1)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
