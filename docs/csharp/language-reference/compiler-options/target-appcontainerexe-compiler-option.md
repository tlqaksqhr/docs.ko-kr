---
title: "/target:appcontainerexe(C# 컴파일러 옵션) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
ms.assetid: e7e62229-23ea-4e53-bef5-380d951bf95f
caps.latest.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 13
---
# /target:appcontainerexe(C# 컴파일러 옵션)
**\/target:appcontainerexe** 컴파일러 옵션을 사용하는 경우 컴파일러에서 응용 프로그램 컨테이너에서 실행해야 하는 Windows 실행 파일\(.exe\)을 만듭니다.  이 옵션은 [\/target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md)와 같지만 [!INCLUDE[win8_appname_long](../../../csharp/includes/win8-appname-long-md.md)] 응용 프로그램을 위해 설계되었습니다.  
  
## 구문  
  
```  
/target:appcontainerexe  
```  
  
## 설명  
 이 옵션은 응용 프로그램이 응용 프로그램 컨테이너에서 실행되도록 하기 위해 [이식 가능한 실행 파일](http://go.microsoft.com/fwlink/p/?LinkId=236960)\(PE\)에 비트를 설정합니다.  해당 비트가 설정된 경우 CreateProcess 메서드가 응용 프로그램 밖에서 실행 파일을 실행하려고 시도하면 오류가 발생합니다.  
  
 [\/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) 옵션을 사용하지 않으면 [Main](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md) 메서드가 포함된 입력 파일의 이름이 출력 파일의 이름으로 사용됩니다.  
  
 이 옵션을 명령 프롬프트에서 지정하면 실행 파일을 만드는 데 다음 **\/out** 또는 **\/target** 옵션까지의 모든 파일이 사용됩니다.  
  
### IDE에서 이 컴파일러 옵션을 설정하려면  
  
1.  **솔루션 탐색기**에서 프로젝트의 바로 가기 메뉴를 열고 **속성**을 선택합니다.  
  
2.  **응용 프로그램** 탭의 **출력 형식** 목록에서 **Windows 스토어 앱**을 선택합니다.  
  
     이 옵션은 [!INCLUDE[win8_appname_long](../../../csharp/includes/win8-appname-long-md.md)] 응용 프로그램 템플릿에서만 사용할 수 있습니다.  
  
 이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.ProjectProperties3.OutputType%2A>을 참조하십시오.  
  
## 예제  
 다음 명령은 `filename.cs`를 응용 프로그램 컨테이너에서만 실행할 수 있는 Windows 실행 파일로 컴파일합니다.  
  
```  
csc /target:appcontainerexe filename.cs  
```  
  
## 참고 항목  
 [\/target \(Specify Output File Format\)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)   
 [\/target:winexe \(Create a Windows Program\)](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md)   
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)