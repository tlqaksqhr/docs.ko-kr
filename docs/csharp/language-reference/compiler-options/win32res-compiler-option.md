---
title: "/win32res (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/win32res"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "win32res compiler option"
  - "/win32res compiler option [C#]"
  - "-win32res compiler option [C#]"
  - "win32res compiler option [C#]"
ms.assetid: 3c33f750-6948-4c7e-a27e-bef98f77255b
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# /win32res (C# Compiler Options)
**\/win32res** 옵션을 사용하여 Win32 리소스를 출력 파일에 삽입할 수 있습니다.  
  
## 구문  
  
```  
/win32res:filename  
```  
  
## 인수  
 `filename`  
 출력 파일에 추가할 리소스 파일입니다.  
  
## 설명  
 Win32 리소스 파일은 [리소스 컴파일러](http://go.microsoft.com/fwlink/?LinkId=148370) 와 함께 생성될 수 있습니다.  리소스 컴파일러는 Visual C\+\+ 프로그램을 컴파일할 때 실행되며 .rc 파일에서 .res 파일이 만들어집니다.  
  
 Win32 리소스는 파일 탐색기에서 응용 프로그램을 식별하는 데 도움을 주는 버전 정보나 비트맵 \(아이콘\) 정보를 포함할 수 있습니다.  **\/win32res**를 지정하지 않으면 컴파일러에서는 어셈블리 버전을 기반으로 버전 정보를 생성합니다.  
  
 .NET Framework 리소스 파일을 참조하려면 [\/linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md)를 참조하고, 추가하려면 [\/resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md)를 참조하십시오.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성** 페이지를 엽니다.  
  
2.  **응용 프로그램** 속성 페이지를 클릭합니다.  
  
3.  **리소스 파일** 단추를 클릭하고 콤보 상자를 사용하여 파일을 선택합니다.  
  
## 예제  
 `in.cs`를 컴파일하고 Win32 리소스 파일 `rf.res`를 연결하여 `in.exe`를 만듭니다.  
  
```  
csc /win32res:rf.res in.cs  
```  
  
## 참고 항목  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/ko-kr/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)