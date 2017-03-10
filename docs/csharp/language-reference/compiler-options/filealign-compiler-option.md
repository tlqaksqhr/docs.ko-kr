---
title: "/filealign (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/filealign"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/alignment compiler option [C#]"
  - "filealign compiler option [C#]"
  - "-filealign compiler option [C#]"
  - "/sections compiler option [C#]"
  - "alignment compiler option [C#]"
  - "sections compiler option [C#]"
  - "-sections compiler option [C#]"
  - "/filealign compiler option [C#]"
  - "file sharing [C#]"
  - "-alignment compiler option [C#]"
  - "section alignment [C#]"
ms.assetid: 15cf1c98-3798-4ced-9f08-60619308a073
caps.latest.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 14
---
# /filealign (C# Compiler Options)
**\/filealign** 옵션을 사용하여 출력 파일의 섹션 크기를 지정할 수 있습니다.  
  
## 구문  
  
```  
/filealign:number  
```  
  
## 인수  
 `number`  
 출력 파일의 섹션 크기를 지정하는 값으로,  유효한 값은 512, 1024, 2048, 4096 및 8192입니다.  이 값은 바이트 단위입니다.  
  
## 설명  
 각 섹션은 **\/filealign** 값의 배수인 경계에 맞춰집니다.  고정된 기본값은 없습니다.  **\/filealign**을 지정하지 않으면 공용 언어 런타임이 컴파일 타임에 기본값을 선택합니다.  
  
 섹션 크기를 지정하면 출력 파일의 크기에 영향을 줍니다.  소형 장치에서 실행되는 프로그램의 경우 섹션 크기 수정 기능이 유용하게 사용될 수 있습니다.  
  
 출력 파일의 섹션에 대한 자세한 내용을 보려면 [DUMPBIN](/visual-cpp/build/reference/dumpbin-options)을 사용하십시오.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성** 페이지를 엽니다.  
  
2.  **빌드** 속성 페이지를 클릭합니다.  
  
3.  **고급** 단추를 클릭합니다.  
  
4.  **파일 맞춤** 속성을 수정합니다.  
  
 이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법은 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.FileAlignment%2A>를 참조하십시오.  
  
## 참고 항목  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/ko-kr/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)