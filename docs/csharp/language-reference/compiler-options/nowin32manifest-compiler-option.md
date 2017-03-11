---
title: "/nowin32manifest (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/nowin32manifest"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "nowin32manifest compiler option [C#]"
  - "-nowin32manifest compiler option [C#]"
  - "/nowin32manifest compiler option [C#]"
ms.assetid: 6f06365b-b87b-46a2-b187-b3bfeaf4862d
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 13
---
# /nowin32manifest (C# Compiler Options)
**\/nowin32manifest** 옵션을 사용하여 응용 프로그램 매니페스트를 실행 파일에 포함하지 않도록 컴파일러에 지시합니다.  
  
## 구문  
  
```  
/nowin32manifest  
```  
  
## 설명  
 이 옵션을 사용할 때 Win32 리소스 파일이나 이후 빌드 단계에서 응용 프로그램 매니페스트를 제공하지 않으면 응용 프로그램이 Windows Vista에서 가상화됩니다.  가상화에 대한 자세한 내용은 [New UAC Technologies for Windows Vista](http://msdn.microsoft.com/ko-kr/80efa4c7-3904-45c5-82e8-2d558fe67db9)를 참조하십시오.  
  
 Visual Studio의 **매니페스트** 드롭다운 목록에서 **매니페스트 없이 응용 프로그램 만들기** 옵션을 선택하여 **응용 프로그램 속성** 페이지에서 이 옵션을 설정합니다.  자세한 내용은 [프로젝트 디자이너, 응용 프로그램 페이지\(C\#\)](/visual-studio/ide/reference/application-page-project-designer-csharp)을 참조하십시오.  
  
 매니페스트 생성에 대한 자세한 내용은 [\/win32manifest \(Import a Custom Win32 Manifest File\)](../../../csharp/language-reference/compiler-options/win32manifest-compiler-option.md)를 참조하십시오.  
  
## 참고 항목  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/ko-kr/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)