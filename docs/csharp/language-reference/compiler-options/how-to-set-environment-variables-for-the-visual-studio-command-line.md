---
title: "방법: Visual Studio 명령줄에 필요한 환경 변수 설정 | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.build.commandline
dev_langs:
- CSharp
helpviewer_keywords:
- csc.exe, command-line builds
- Visual C#, command-line builds
- command-line compilers, Visual C#
- Vsvars32.bat
- builds [C#], command-line
- compilers, invoking from command line
- Vcvars32.bat file
- command line [C#], building from
- Visual C# compiler, enabling
- compiling source code, from command line
ms.assetid: 7ec09480-5612-4f6a-8d00-ad90ea9bca5d
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: Human Translation
ms.sourcegitcommit: a780a11d8dd238187eb82933359bbb151bb3c333
ms.openlocfilehash: e2cc644bb3b2c51615fe763224505b07e113ad62
ms.contentlocale: ko-kr
ms.lasthandoff: 05/22/2017

---
# <a name="how-to-set-environment-variables-for-the-visual-studio-command-line"></a>방법: Visual Studio 명령줄에 필요한 환경 변수 설정
vsvars32.bat 파일은 명령줄 빌드를 사용하도록 적절한 환경 변수를 설정합니다. vsvars32.bat에 대한 자세한 내용은 [기술 자료 문서 Q248802](http://go.microsoft.com/fwlink/?LinkId=225042)를 참조하세요.  
  
 Visual Studio의 이전 버전이 설치된 컴퓨터에 Visual Studio의 최신 버전을 설치한 경우 동일한 명령 프롬프트 창에서 다른 버전의 vsvars32.bat 또는 vcvars32.bat를 실행해서는 안 됩니다.  
  
### <a name="to-run-vsvars32bat"></a>VSVARS32.BAT를 실행하려면  
  
1.  **시작** 메뉴에서 **VS2012용 개발자 명령 프롬프트**를 엽니다.  
  
2.  경로를 설치되어 있는 Visual Studio의 Program Files\Microsoft Visual Studio *Version*\Common7\Tools 또는 Program Files (x86)\Microsoft Visual Studio *Version*\Common7\Tools 하위 디렉터리로 변경합니다.  
  
3.  **VSVARS32**를 입력하여 VSVARS32.bat를 실행합니다.  
  
    > [!CAUTION]
    >  VSVARS32.bat는 컴퓨터마다 다를 수 있습니다. 누락되거나 손상된 VSVARS32.bat 파일을 다른 컴퓨터의 VSVARS32.bat 파일로 바꾸지 마세요. 대신 설치 프로그램을 다시 실행하여 누락된 파일을 교체하십시오.  
  
## <a name="see-also"></a>참고 항목  
 [csc.exe를 사용한 명령줄 빌드](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)
