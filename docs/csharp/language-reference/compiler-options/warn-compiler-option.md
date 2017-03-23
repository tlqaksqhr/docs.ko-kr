---
title: "/warn (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/warn"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "warning level [C#]"
  - "/w compiler option [C#]"
  - "-w compiler option [C#]"
  - "-warn compiler option [C#]"
  - "/warn compiler option [C#]"
  - "w compiler option [C#]"
  - "warn compiler option [C#]"
ms.assetid: 5f80ff59-4991-4382-9f9a-77da18446e71
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# /warn (C# Compiler Options)
**\/warn** 옵션을 사용하여 표시할 컴파일러 경고 수준을 지정할 수 있습니다.  
  
## 구문  
  
```  
/warn:option  
```  
  
## 인수  
 `option`  
 컴파일에 대해 원하는 경고 수준이 표시되었습니다. 낮은 숫자는 심각한 경고만 표시하고 높은 숫자는 보다 많은 경고를 표시합니다.  유효한 값은 0\-4입니다.  
  
|경고 수준|의미|  
|-----------|--------|  
|0|모든 경고 메시지를 표시하지 않습니다.|  
|1|심각한 경고 메시지만 표시합니다.|  
|2|수준 1 경고와, 클래스 멤버 숨김 경고 등의 비교적 심각하지 않은 특정 경고를 표시합니다.|  
|3|수준 2 경고와 항상 `true`나 `false`로 평가되는 식에 대한 경고 같은 비교적 심각하지 않은 특정 경고를 표시합니다.|  
|4\(기본값\)|모든 수준 3 경고와 정보를 알려 주는 경고를 표시합니다.|  
  
## 설명  
 오류 또는 경고에 대한 정보를 보려면 도움말 색인에서 오류 코드를 찾습니다.  오류 또는 경고에 대한 정보를 얻는 다른 방법에 대해서는 [C\# Compiler Errors](../../../csharp/language-reference/compiler-messages/index.md)를 참조하십시오.  
  
 모든 경고를 오류로 처리하려면 [\/warnaserror](../../../csharp/language-reference/compiler-options/warnaserror-compiler-option.md)를 사용합니다.  특정 경고를 비활성화하려면 [\/nowarn](../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md)을 사용합니다.  
  
 **\/w**는 **\/warn**의 약식 표현입니다.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성** 페이지를 엽니다.  
  
2.  **빌드** 속성 페이지를 클릭합니다.  
  
3.  **경고 수준** 속성을 수정합니다.  
  
 이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법은 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A>을 참조하십시오.  
  
## 예제  
 `in.cs`를 컴파일하고 컴파일러에서 수준 1의 경고만 표시하도록 합니다.  
  
```  
csc /warn:1 in.cs  
```  
  
## 참고 항목  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/ko-kr/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)