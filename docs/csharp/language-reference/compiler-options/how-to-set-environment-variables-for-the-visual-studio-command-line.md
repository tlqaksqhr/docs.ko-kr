---
title: "방법: Visual Studio 명령줄에 필요한 환경 변수 설정"
ms.date: 09-29-2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: cs.build.commandline
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
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8012e310bb04ec3acef0790f9cd50ed42dd9286a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-set-environment-variables-for-the-visual-studio-command-line"></a>방법: Visual Studio 명령줄에 필요한 환경 변수 설정

VsDevCmd.bat 파일 명령줄 빌드 적절 한 환경 변수를 설정 합니다. VsDevCmd.bat에 대 한 자세한 내용은 참조 [기술 자료 문서 Q248802](http://go.microsoft.com/fwlink/?LinkId=225042)합니다.  

> [!NOTE]
> VsDevCmd.bat 파일은 Visual Studio 2017와 함께 제공 하는 새 파일. Visual Studio 2015 및 이전 버전에 같은 목적을 위해 VSVARS32.bat를 사용 합니다. 이 파일은 \program files\microsoft Visual Studio 저장 된\\*버전*\Common7\Tools or Program Files (x86) \Microsoft Visual Studio\\*버전*\Common7\Tools 합니다.
  
또한 Visual Studio의 이전 버전을 보유 하는 컴퓨터에서 현재 버전의 Visual Studio가 설치 되어 VsDevCmd.bat와 VSVARS32 하지 실행 해야 합니다. 동일한 명령 프롬프트 창에서 서로 다른 버전에서 BAT 합니다. 대신 별도 창에서 각 버전에 대해 명령을 실행 해야 합니다.
  
### <a name="to-run-vsdevcmdbat"></a>VsDevCmd.BAT를 실행 하려면  
  
1.  **시작** 메뉴를 열고는 **VS 2017 용 개발자 명령 프롬프트**합니다.  에 **Visual Studio 2017** 폴더입니다.
  
2.  Files\microsoft Visual Studio로 변경\\*버전*\\*제공*\Common7\Tools or \Program 파일 (x86) \Microsoft Visual Studio\\ *버전*\\*제공*\Common7\Tools 하위 설치 합니다.  (*버전* 은 *2017* 현재 버전에 대 한 합니다. *제공* 중 하나인 *엔터프라이즈*, *Professional* 또는 *커뮤니티*.)
  
3.  VsDevCmd.bat 입력 하 여 실행 **VsDevCmd**합니다.  
  
    > [!CAUTION]
    >  VsDevCmd.bat 컴퓨터 마다 다를 수 있습니다. 다른 컴퓨터에서 VsDevCmd.bat VsDevCmd.bat 파일이 없거나 손상 된 대체 하지 않습니다. 대신 설치 프로그램을 다시 실행하여 누락된 파일을 교체하십시오.  
  
## <a name="see-also"></a>참고 항목  
 [csc.exe를 사용한 명령줄 빌드](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)
