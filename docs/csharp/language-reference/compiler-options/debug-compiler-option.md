---
title: "/debug (C# Compiler Options) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/debug"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "debug compiler option [C#]"
  - "-debug compiler option [C#]"
  - "/debug compiler option [C#]"
ms.assetid: e2b48c07-01bc-45cc-a52c-92e9085eb969
caps.latest.revision: 19
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /debug (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

**\/debug** 옵션을 사용하면 컴파일러에서 디버깅 정보를 생성하여 출력 파일에 저장합니다.  
  
## 구문  
  
```  
/debug[+ | -]  
/debug:{full | pdbonly}  
```  
  
## 인수  
 `+` &#124; `-`  
 `+`를 지정하거나 **\/debug**만 사용하면 컴파일러에서 디버깅 정보를 생성하여 프로그램 데이터베이스\(.pdb 파일\)에 저장합니다.  `-`를 지정하면 디버깅 정보가 생성되지 않으며 **\/debug**를 지정하지 않은 것과 같습니다.  
  
 `full` &#124; `pdbonly`  
 컴파일러에서 생성되는 디버깅 정보 형식을 지정합니다.  full 인수를 사용하면 실행 프로그램에 디버거가 연결되며 **\/debug:pdbonly**를 지정하지 않은 것과 같습니다.  pdbonly를 지정하면 프로그램을 디버거에서 시작할 때 소스 코드를 디버깅할 수 있지만 실행 프로그램을 디버거에 연결할 때는 어셈블러만 표시됩니다.  
  
## 설명  
 이 옵션을 사용하면 디버그 빌드를 만들 수 있습니다.  **\/debug**, **\/debug\+** 또는 **\/debug:full**을 지정하지 않으면 프로그램의 출력 파일을 디버깅할 수 없습니다.  
  
 **\/debug:full**을 사용하는 경우에는 JIT 최적화된 코드의 속도와 크기에 영향이 있고 **\/debug:full**이 포함된 코드 품질에도 영향을 미친다는 점에 유의해야 합니다.  따라서, 시험판 코드를 생성할 경우 **\/debug:pdbonly**를 사용하거나 PDB를 사용하지 않는 것이 좋습니다.  
  
> [!NOTE]
>  **\/debug:pdbonly**와 **\/debug:full** 사이에는 한 가지 차이점이 있습니다. 즉, **\/debug:full**을 사용할 경우 컴파일러에서는 디버그 정보를 사용할 수 있음을 JIT 컴파일러에 알려주는 <xref:System.Diagnostics.DebuggableAttribute>를 생성합니다.  따라서 **\/debug:full**을 사용하는 경우 코드에 <xref:System.Diagnostics.DebuggableAttribute>가 false로 설정되어 있으면 오류가 발생합니다.  
  
 응용 프로그램의 디버깅 성능을 구성하는 방법에 대한 자세한 내용은 [쉽게 디버깅할 수 있도록 이미지 만들기](../Topic/Making%20an%20Image%20Easier%20to%20Debug.md)를 참조하십시오.  
  
 .pdb 파일의 위치를 변경하려면 [\/pdb \(Specify Debug Symbol File\)](../../../csharp/language-reference/compiler-options/pdb-compiler-option.md)를 참조하십시오.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성** 페이지를 엽니다.  
  
2.  **빌드** 속성 페이지를 클릭합니다.  
  
3.  **고급** 단추를 클릭합니다.  
  
4.  **디버그 정보** 속성을 수정합니다.  
  
 이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법은 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DebugSymbols%2A>을 참조하십시오.  
  
## 예제  
 디버깅 정보를 출력 파일 `app.pdb`에 저장합니다.  
  
```  
csc /debug /pdb:app.pdb test.cs  
```  
  
## 참고 항목  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/ko-kr/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)