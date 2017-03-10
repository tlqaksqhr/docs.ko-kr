---
title: "#pragma checksum(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "#pragma checksum"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "#pragma checksum[C#]"
ms.assetid: 3673e4ca-6098-4ec1-890f-8fceb2a794a2
caps.latest.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 11
---
# #pragma checksum(C# 참조)
[!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp-md.md)] 페이지의 원활한 디버깅을 위해 소스 파일에 대한 체크섬을 생성합니다.  
  
## 구문  
  
```  
#pragma checksum "filename" "{guid}" "checksum bytes"  
```  
  
#### 매개 변수  
 `"filename"`  
 변경 또는 업데이트 내용을 모니터링해야 하는 파일의 이름입니다.  
  
 `"{guid}"`  
 파일의 GUID\(Globally Unique Identifier\)입니다.  
  
 `"checksum_bytes"`  
 체크섬의 바이트를 나타내는 16진수 문자열입니다.  이 문자열은 16진수 짝수여야 합니다.  홀수이면 컴파일 타임 경고가 발생하고 지시문이 무시됩니다.  
  
## 설명  
 Visual Studio 디버거에서는 항상 올바른 소스를 찾을 수 있도록 체크섬을 사용합니다.  컴파일러에서는 소스 파일의 체크섬을 계산하여 결과를 PDB\(프로그램 데이터베이스\) 파일에 내보냅니다.  그러면 디버거에서는 PDB를 사용하여 소스 파일에 대해 계산한 체크섬과 비교합니다.  
  
 [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp-md.md)] 프로젝트의 경우에는 .aspx 파일이 아니라 생성된 소스 파일에 대해 체크섬이 계산되므로 이는 효과적인 방법이 아닙니다.  이 문제를 해결하기 위해 `#pragma checksum`은 [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp-md.md)] 페이지에 대한 체크섬을 지원합니다.  
  
 [!INCLUDE[csprcs](../../../csharp/includes/csprcs-md.md)]에서 [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp-md.md)] 프로젝트를 만들면 생성된 소스 파일에는 소스를 생성하는 데 사용된 .aspx 파일에 대한 체크섬이 포함됩니다.  그런 다음 컴파일러에서 이 정보를 PDB 파일에 씁니다.  
  
 파일에 `#pragma checksum` 지시문이 없으면 컴파일러에서 체크섬을 계산하고 해당 값을 PDB 파일에 씁니다.  
  
## 예제  
  
```  
class TestClass  
{  
    static int Main()  
    {  
        #pragma checksum "file.cs" "{3673e4ca-6098-4ec1-890f-8fceb2a794a2}" "{012345678AB}" // New checksum  
    }  
}  
```  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 전처리기 지시문](../../../csharp/language-reference/preprocessor-directives/index.md)