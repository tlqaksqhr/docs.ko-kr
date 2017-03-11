---
title: "/win32icon (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/win32icon"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "win32icon compiler option [C#]"
  - "/win32icon compiler option [C#]"
  - "-win32icon compiler option [C#]"
ms.assetid: 756d9b6d-ab07-41b7-ba58-5bd88f711138
caps.latest.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 18
---
# /win32icon (C# Compiler Options)
**\/win32icon** 옵션을 사용하면 파일 탐색기에서 출력 파일이 원하는 모습으로 나타나도록 .ico 파일을 출력 파일에 삽입할 수 있습니다.  
  
## 구문  
  
```  
/win32icon:filename  
```  
  
## 인수  
 `filename`  
 출력 파일에 추가할 .ico 파일입니다.  
  
## 설명  
 .ico 파일은 [리소스 컴파일러](http://go.microsoft.com/fwlink/?LinkId=148370)와 함께 만들어 질 수 있습니다.  리소스 컴파일러는 Visual C\+\+ 프로그램을 컴파일할 때 실행되며 .rc 파일에서 .ico 파일이 만들어집니다.  
  
 .NET Framework 리소스 파일을 참조하려면 [\/linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md)를 참조하고, 추가하려면 [\/resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md)를 참조하십시오.  .res 파일을 가져오려면 [\/win32res](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md)를 참조하십시오.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성** 페이지를 엽니다.  
  
2.  **응용 프로그램** 속성 페이지를 클릭합니다.  
  
3.  **응용 프로그램 아이콘** 속성을 수정합니다.  
  
 이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법은 <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A>을 참조하십시오.  
  
## 예제  
 `in.cs`를 컴파일하고 `rf.ico`파일을 추가하여 `in.exe`를 만듭니다.  
  
```  
csc /win32icon:rf.ico in.cs  
```  
  
## 참고 항목  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/ko-kr/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)