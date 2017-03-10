---
title: "/pdb (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/pdb"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "-pdb compiler option [C#]"
  - "pdb compiler option [C#]"
  - "/pdb compiler option [C#]"
ms.assetid: e9d0f96a-5b75-45d6-9765-92538dd5f823
caps.latest.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 8
---
# /pdb (C# Compiler Options)
**\/pdb** 컴파일러 옵션은 디버그 기호 파일의 이름과 위치를 지정합니다.  
  
## 구문  
  
```  
/pdb:filename  
```  
  
## 인수  
 `filename`  
 디버그 기호 파일의 이름과 위치입니다.  
  
## 설명  
 [\/debug \(Emit Debugging Information\)](../../../csharp/language-reference/compiler-options/debug-compiler-option.md)를 지정하면 컴파일러는 출력 파일\(.exe 또는 .dll\)을 만드는 것과 동일한 디렉터리에 출력 파일의 이름과 동일한 파일 이름의 .pdb 파일을 만듭니다.  
  
 **\/pdb**를 사용하면 .pdb 파일에 기본이 아닌 파일 이름과 위치를 지정할 수 있습니다.  
  
 이 컴파일러 옵션은 Visual Studio 개발 환경에서 설정할 수 없으며 프로그램 방식으로 변경할 수도 없습니다.  
  
## 예제  
 `t.cs`를 컴파일하고 tt.pdb라는 .pdb 파일을 만듭니다.  
  
```  
csc /debug /pdb:tt t.cs  
```  
  
## 참고 항목  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/ko-kr/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)