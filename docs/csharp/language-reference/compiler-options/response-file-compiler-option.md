---
title: "@ (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "@"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "response files, specifying for compilation [C#]"
  - "@ compiler option"
ms.assetid: dda4fa9f-a02c-400f-8b6a-d58834e13d7f
caps.latest.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 9
---
# @ (C# Compiler Options)
@ 옵션을 사용하여 컴파일러 옵션과 컴파일할 소스 코드 파일 목록을 포함하는 파일을 지정할 수 있습니다.  
  
## 구문  
  
```  
@response_file  
```  
  
## 인수  
 `response_file`  
 컴파일러 옵션이나 컴파일할 소스 코드 파일 목록이 들어 있는 파일입니다.  
  
## 설명  
 컴파일러는 이 컴파일러 옵션과 소스 코드 파일을 명령줄에 지정된 것처럼 처리합니다.  
  
 컴파일할 때 두 개 이상의 지시 파일을 지정하려면 여러 지시 파일 옵션을 지정합니다.  예를 들면 다음과 같습니다.  
  
```  
@file1.rsp @file2.rsp  
```  
  
 지시 파일에 여러 컴파일러 옵션과 소스 코드 파일을 한 줄로 나타낼 수 있습니다.  하나의 컴파일러 옵션 지정은 여러 줄로 나타낼 수 없으며 반드시 한 줄로 나타내야 합니다.  지시 파일은 \# 기호로 시작하는 주석을 포함할 수 있습니다.  
  
 지시 파일 내에서 컴파일러 옵션을 지정하는 것은 명령줄에서 해당 명령을 실행하는 것과 같습니다.  자세한 내용은 [명령줄에서 빌드](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md)를 참조하십시오.  
  
 컴파일러는 명령 옵션을 발견하면 처리합니다.  따라서 명령줄 인수로 지시 파일에 있는 이전의 옵션 목록을 재정의할 수 있습니다.  반대로 지시 파일에 있는 옵션으로 명령줄이나 다른 지시 파일에 있는 이전의 옵션 목록을 재정의할 수 있습니다.  
  
 C\#에서는 csc.rsp 파일을 제공합니다. 이 파일은 csc.exe 파일과 같은 디렉터리에 있습니다.  csc.rsp에 대한 자세한 내용은 [\/noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md)를 참조하십시오.  
  
 이 컴파일러 옵션은 Visual Studio 개발 환경에서 설정할 수 없으며 프로그램 방식으로 변경할 수도 없습니다.  
  
## 예제  
 다음은 샘플 지시 파일의 일부입니다.  
  
```  
# build the first output file  
/target:exe /out:MyExe.exe source1.cs source2.cs  
```  
  
## 참고 항목  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)