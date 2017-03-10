---
title: "Debugging Your Visual Basic Application | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "debugging [Visual Basic], common tasks"
ms.assetid: 904760b8-9fe9-42a7-9d65-d93774253219
caps.latest.revision: 28
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 28
---
# Debugging Your Visual Basic Application
[!INCLUDE[vs2017banner](../../visual-basic/developing-apps/includes/vs2017banner.md)]

이 페이지는 [!INCLUDE[vsprvs](../../csharp/includes/vsprvs-md.md)]에 기본 제공되는 디버깅 기능에 대한 설명서에 대한 링크를 제공합니다.  예를 들어 디버거 자체에서 런타임 동작을 관찰하여 응용 프로그램에서 의미 오류를 찾을 수 있습니다.  
  
 디버거를 사용하면 추가로 호출을 삽입하여 값을 출력하지 않아도 응용 프로그램의 변수 내용을 검사할 수 있습니다.  이와 유사하게 코드에 중단점을 삽입하여 지정하는 위치에서 실행을 중지시킬 수 있습니다.  
  
## 실행 제어  
 다음 표에서는 실행 제어와 관련된 디버깅 작업을 나열하고 이와 관련된 도움말 페이지의 링크를 제공합니다.  
  
|||  
|-|-|  
|To|참조|  
|Visual Studio 프로젝트 디버깅, 프로세스에 연결, 코드 중단, 단계별 코드 실행, 커서까지 실행, 호출 스택의 함수까지 실행, 다음 문 설정, 내 코드만 단계별 실행, 디버깅 중지, 디버깅 다시 시작 또는 디버깅된 프로세스에서 분리를 시작합니다.|[디버거로 코드 탐색](/visual-studio/debugger/navigating-through-code-with-the-debugger)|  
|프로그램의 디버그 버전 및 릴리스 버전에 대한 구성을 지정합니다.|[Debug and Release Project Configurations](http://msdn.microsoft.com/ko-kr/0440b300-0614-4511-901a-105b771b236e)|  
|시작 옵션을 설정합니다\(명령줄 인수, 작업 디렉터리, 원격 컴퓨터\).|[NIB: How to: Set Start Options for Application Debugging](http://msdn.microsoft.com/ko-kr/ce792058-7bac-4dd6-858b-466e872687b8)|  
|디자인 타임에 디버깅합니다.|[연습: 디자인 타임에 디버깅](../Topic/Walkthrough:%20Debugging%20at%20Design%20Time.md)|  
|Visual Studio 외부에서 실행 중인 프로그램에 치명적 오류가 발생할 경우 Visual Studio 디버거를 시작하는 JIT\(Just\-In\-Time\) 디버깅을 활성화합니다.|[Just\-In\-Time 디버깅](/visual-studio/debugger/just-in-time-debugging-in-visual-studio)|  
|소스 줄, 어셈블리 명령 및 호출 스택 함수에서 중단점을 설정합니다.  조건, 적중된 횟수 및 실행 위치를 지정합니다.|[중단점 사용](/visual-studio/debugger/using-breakpoints)|  
  
## 예외 처리  
 다음 표에서는 예외 처리와 관련된 디버깅 작업을 나열하고 이와 관련된 도움말 페이지로 안내합니다.  
  
|||  
|-|-|  
|To|참조|  
|처리되지 않은 예외에서 중단합니다.|[방법: 사용자가 처리하지 않은 예외에서 중단](../Topic/How%20to:%20Break%20on%20User-Unhandled%20Exceptions.md)|  
|예외가 throw되었을 때 중단합니다.|[방법: 예외가 throw되었을 때 중단](../Topic/How%20to:%20Break%20When%20an%20Exception%20is%20Thrown.md)|  
|첫째 예외에서 중단합니다.|[방법: 예외가 throw되었을 때 중단](../Topic/How%20to:%20Break%20When%20an%20Exception%20is%20Thrown.md)|  
|예외 도우미를 사용합니다.|[How to: Correct Run\-Time Errors with the Exception Assistant](../Topic/How%20to:%20Correct%20Run-Time%20Errors%20with%20the%20Exception%20Assistant.md)|  
|새 예외를 추가합니다.|[방법: 새 예외 추가](../Topic/How%20to:%20Add%20New%20Exceptions.md)|  
|예외가 throw된 후 실행을 계속합니다.|[예외 후 실행 계속](/visual-studio/debugger/continuing-execution-after-an-exception)|  
  
## 편집하며 계속하기  
 다음 표에서는 편집하며 계속하기와 관련된 디버깅 작업을 나열하고 이와 관련된 도움말 페이지로 안내합니다.  
  
|||  
|-|-|  
|To|참조|  
|편집하며 계속하기 기능을 켜고 끕니다.|[방법: 편집하며 계속하기 설정\/해제](../Topic/How%20to:%20Enable%20and%20Disable%20Edit%20and%20Continue.md)|  
|코드 변경 내용을 적용하는 도중 편집하며 계속하기를 중지합니다.|[방법: 코드 변경 중지](../Topic/How%20to:%20Stop%20Code%20Changes.md)|  
|중단 모드에서 편집을 적용합니다.|[방법: 편집하며 계속하기를 사용하여 중단 모드에서 편집 적용](../Topic/How%20to:%20Apply%20Edits%20in%20Break%20Mode%20with%20Edit%20and%20Continue.md)|  
  
## 디버깅 데이터 검사  
 다음 표에서는 디버깅 데이터 보기와 관련된 디버깅 작업을 나열하고 이와 관련된 도움말 페이지로 안내합니다.  
  
|||  
|-|-|  
|To|참조|  
|**레지스터** 창을 사용하여 레지스터 내용을 표시합니다.|[방법: 레지스터 창 사용](../Topic/How%20to:%20Use%20the%20Registers%20Window.md)|  
|**호출 스택** 창을 사용하여 현재 스택에 있는 함수 또는 프로시저 호출을 봅니다.|[방법: 호출 스택 창 사용](../Topic/How%20to:%20Use%20the%20Call%20Stack%20Window.md)|  
|**디스어셈블리** 창을 사용하여 컴파일러에서 만든 명령에 해당하는 어셈블리 코드를 봅니다.|[방법: 디스어셈블리 창 사용](../Topic/How%20to:%20Use%20the%20Disassembly%20Window.md)|  
|**모듈** 창을 사용하여 프로그램에 사용되는 모듈을 나열하고 설명합니다.|[방법: 모듈 창 사용](../Topic/How%20to:%20Use%20the%20Modules%20Window.md)|  
|**스크립트 탐색기** 창을 사용하여 현재 프로그램에 로드된 스크립트 파일을 나열합니다.|[방법: 스크립트 문서 보기](../Topic/How%20to:%20View%20Script%20Documents.md)|  
|**스레드** 창을 사용하여 프로그램의 스레드를 검사하고 제어합니다.|[방법: 스레드 창 사용](../Topic/How%20to:%20Use%20the%20Threads%20Window.md)|  
  
## 참고 항목  
 [연습: Windows Form 디버깅](../Topic/Walkthrough:%20Debugging%20a%20Windows%20Form.md)   
 [관리 코드 디버깅](/visual-studio/debugger/debugging-managed-code)   
 [네이티브 코드 디버깅](/visual-studio/debugger/debugging-native-code)   
 [웹 응용 프로그램 및 스크립트 디버깅](/visual-studio/debugger/debugging-web-applications-and-script)   
 [사용자 인터페이스 참조 디버깅](/visual-studio/debugger/debugging-user-interface-reference)   
 [디버그 설정 및 준비](/visual-studio/debugger/debugger-settings-and-preparation)   
 [디버거 기본 사항](/visual-studio/debugger/debugger-basics)   
 [디버거로 코드 탐색](/visual-studio/debugger/navigating-through-code-with-the-debugger)   
 [IntelliTrace 사용](/visual-studio/debugger/intellitrace)   
 [C\#, F\# 및 Visual Basic 프로젝트 형식](../Topic/Debugging%20Preparation:%20C%23,%20F%23,%20and%20Visual%20Basic%20Project%20Types.md)   
 [방법: 편집하며 계속하기를 사용하여 중단 모드에서 편집 적용](../Topic/How%20to:%20Apply%20Edits%20in%20Break%20Mode%20with%20Edit%20and%20Continue.md)