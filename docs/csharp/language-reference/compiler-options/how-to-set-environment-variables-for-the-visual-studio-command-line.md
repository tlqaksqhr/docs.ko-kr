---
title: "How to: Set Environment Variables for the Visual Studio Command Line | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "cs.build.commandline"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "csc.exe, command-line builds"
  - "Visual C#, command-line builds"
  - "command-line compilers, Visual C#"
  - "Vsvars32.bat"
  - "builds [C#], command-line"
  - "compilers, invoking from command line"
  - "Vcvars32.bat file"
  - "command line [C#], building from"
  - "Visual C# compiler, enabling"
  - "compiling source code, from command line"
ms.assetid: 7ec09480-5612-4f6a-8d00-ad90ea9bca5d
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# How to: Set Environment Variables for the Visual Studio Command Line
vsvars32.bat 파일은 명령줄 빌드를 사용하도록 적절한 환경 변수를 설정합니다.  vsvars32.bat에 대한 자세한 내용은 [기술 자료 문서 Q248802](http://go.microsoft.com/fwlink/?LinkId=225042)를 참조하세요.  
  
 Visual Studio의 이전 버전이 설치된 컴퓨터에 Visual Studio의 최신 버전을 설치한 경우 동일한 명령 프롬프트 창에서 다른 버전의 vsvars32.bat 또는 vcvars32.bat를 실행해서는 안 됩니다.  
  
### VSVARS32.BAT를 실행하려면  
  
1.  **시작** 메뉴에서 **VS2012용 개발자 명령 프롬프트**를 엽니다.  
  
2.  설치의 Program Files\\Microsoft Visual Studio *버전*\\Common7\\Tools or Program Files \(x86\)\\Microsoft Visual Studio *버전*\\Common7\\Tools 하위 디렉터리로 변경합니다.  
  
3.  VSVARS32를 입력하여 VSVARS32.bat를 실행합니다.  
  
    > [!CAUTION]
    >  VSVARS32.bat는 컴퓨터마다 다를 수 있습니다.  누락되거나 손상된 VSVARS32.bat 파일을 다른 컴퓨터의 VSVARS32.bat 파일로 바꾸지 마세요.  대신 설치 프로그램을 다시 실행하여 누락된 파일을 교체하십시오.  
  
## 참고 항목  
 [Command\-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)