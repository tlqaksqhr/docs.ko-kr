---
title: "/errorreport (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/errorreport"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "-errorreport compiler option [C#]"
  - "errorreport compiler option [C#]"
  - "/errorreport compiler option [C#]"
ms.assetid: bd0e7493-b79d-4369-9c3f-ba26ebdfbedf
caps.latest.revision: 35
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 35
---
# /errorreport (C# Compiler Options)
이 옵션을 사용하면 C\# 내부 컴파일러 오류를 Microsoft에 손쉽게 보고할 수 있습니다.  
  
> [!NOTE]
>  Windows Vista 및 Windows Server 2008에서는 Visual Studio에 대한 오류 보고 설정을 지정하더라도 WER\(Windows Error Reporting\)을 통해 지정한 설정이 재정의되지 않습니다.  WER 설정은 Visual Studio 오류 보고 설정보다 항상 우선 순위가 높습니다.  
  
## 구문  
  
```  
/errorreport:{ none | prompt | queue | send }  
```  
  
## 인수  
 **none**  
 내부 컴파일러 오류에 대한 보고서를 수집하거나 Microsoft로 보내지 않습니다.  
  
 **prompt**  
 내부 컴파일러 오류가 발생하면 보고서를 보내는 메시지를 표시합니다.  **prompt**는 개발 환경에서 응용 프로그램을 컴파일할 때 기본값입니다.  
  
 **queue**  
 오류 보고서를 대기시킵니다.  관리자 자격 증명으로 로그온하면 마지막으로 로그온한 이후 발생한 모든 오류를 보고할 수 있습니다.  사용자가 3일에 한 번 이상 오류에 대한 보고서를 보내도록 묻는 메시지가 나타나지 않습니다.  **queue**는 명령줄에서 응용 프로그램을 컴파일할 때 기본값입니다.  
  
 **send**  
 내부 컴파일러 오류 보고서를 자동으로 Microsoft에 보냅니다.  이 옵션을 사용하려면 먼저 Microsoft의 데이터 수집 정책에 동의해야 합니다.  컴퓨터에서 처음으로 **\/errorreport:send**를 지정하면 Microsoft의 데이터 수집 정책이 있는 웹 사이트로 연결되는 컴파일러 메시지가 나타납니다.  
  
 이 옵션은 레지스트리 설정에 따라 달라집니다.  레지스트리에 적절한 값을 설정하는 방법은, MSDN 웹 사이트의 [How to Turn on Automatic Error Reporting in Visual Studio 2008 Command\-line Tools](http://go.microsoft.com/fwlink/?LinkID=184695) 를 참조하십시오.  
  
## 설명  
 ICE\(내부 컴파일러 오류\)는 컴파일러에서 소스 코드 파일을 처리할 수 없을 때 발생합니다.  ICE가 발생하면 컴파일러는 코드를 수정하는 데 유용한 진단 정보나 출력 파일을 생성하지 않습니다.  
  
 이전 릴리스에서는 ICE가 발생한 경우 Microsoft 기술 지원 서비스에 연락하여 문제점을 보고하라는 메시지가 표시되었습니다.  **\/errorreport**를 사용하면 Visual C\# 팀에 ICE 정보를 제공할 수 있습니다.  오류 보고서는 다음에 릴리스될 컴파일러를 개선하는 데 도움이 됩니다.  
  
 사용자가 보고서를 보낼 수 있는지 여부는 컴퓨터 및 사용자 정책 권한에 따라 다릅니다.  
  
 오류 디버거에 대한 자세한 내용은, [Windows \(Drwtsn32.exe\) 도구에 대한 Watson 박사의 설명](http://go.microsoft.com/fwlink/?LinkId=147286) 를 참조하십시오.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성** 페이지를 엽니다.  자세한 내용은 [프로젝트 디자이너, 빌드 페이지\(C\#\)](/visual-studio/ide/reference/build-page-project-designer-csharp)을 참조하십시오.  
  
2.  **빌드** 속성 페이지를 클릭합니다.  
  
3.  **고급** 단추를 클릭합니다.  
  
4.  **내부 컴파일러 오류 보고** 속성을 수정합니다.  
  
 이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.ErrorReport%2A>을 참조하십시오.  
  
## 참고 항목  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)