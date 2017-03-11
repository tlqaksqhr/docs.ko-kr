---
title: "/langversion (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/langversion"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/langversion compiler option [C#]"
  - "-langversion compiler option [C#]"
  - "langversion compiler option [C#]"
ms.assetid: 3fb00b05-a0ff-4782-b313-13a4c0f62d94
caps.latest.revision: 33
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 33
---
# /langversion (C# Compiler Options)
컴파일러에서 선택한 C\# 언어 사양에 포함된 구문만 허용하도록 합니다.  
  
## 구문  
  
```  
/langversion:option  
```  
  
## 인수  
 `option`  
 유효한 값은 다음과 같습니다.  
  
|옵션|의미|  
|--------|--------|  
|default|컴파일러는 모든 유효한 언어 구문을 허용합니다.|  
|ISO\-1|컴파일러에서 ISO\/IEC 23270:2003 C\# 언어 사양에 포함된 구문만 허용합니다.|  
|ISO\-2|컴파일러에서 ISO\/IEC 23270:2006 C\# 언어 사양에 포함된 구문만 허용합니다.  이 사양은 [ISO](http://go.microsoft.com/fwlink/?LinkId=144406) 웹 사이트에서 가능합니다.|  
|3|컴파일러에서 버전 3.0 [C\# 언어 사양](../../../csharp/language-reference/language-specification.md)에 포함된 구문만 허용합니다.|  
  
## 설명  
 C\# 응용 프로그램에서 참조하는 메타데이터에는 **\/langversion** 컴파일러 옵션이 적용되지 않습니다.  
  
 각 버전의 C\# 컴파일러에는 언어 사양에 대한 확장이 포함되어 있으므로 **\/langversion**을 사용해도 이전 버전의 컴파일러와 동일한 기능이 제공되는 것은 아닙니다.  
  
 사용하는 **\/langversion** 설정과 관계없이 현재 버전의 공용 언어 런타임을 사용하여 .exe 또는 .dll을 만듭니다.  여기서 한 가지 예외는 **\/langversion:ISO\-1**에서 작동하는 friend 어셈블리와 [\/moduleassemblyname \(Specify Friend Assembly for Module\)](../../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md)입니다.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성** 페이지를 엽니다.  
  
2.  **빌드** 속성 페이지를 클릭합니다.  
  
3.  **고급** 단추를 클릭합니다.  
  
4.  **언어 버전** 속성을 수정합니다.  
  
 이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>을 참조하십시오.  
  
## 참고 항목  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/ko-kr/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [C\# 언어 사양](../../../csharp/language-reference/language-specification.md)