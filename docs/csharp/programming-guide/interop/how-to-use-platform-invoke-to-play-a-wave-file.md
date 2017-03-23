---
title: "방법: 플랫폼 호출을 사용하여 웨이브 파일 재생(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - ".wav 파일"
  - "상호 운용성[C#], pinvoke를 사용하여 WAV 파일 재생"
  - "플랫폼 호출, 사운드 파일"
  - "wav 파일"
ms.assetid: f7f62f53-e026-4c40-b221-3a26adb0c2c5
caps.latest.revision: 30
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 30
---
# 방법: 플랫폼 호출을 사용하여 웨이브 파일 재생(C# 프로그래밍 가이드)
다음 C\# 코드 예제에서는 플랫폼 호출 서비스를 사용하여 Windows 운영 체제에서 웨이브 사운드 파일을 재생하는 방법을 보여 줍니다.  
  
## 예제  
 이 예제 코드에서는 `DllImport`를 사용하여 `winmm.dll`의 `PlaySound` 메서드 진입점을 `Form1 PlaySound()`로 가져옵니다.  이 예제에는 단추 하나가 있는 간단한 Windows Form이 있습니다.  단추를 클릭하면 재생할 파일을 열 수 있도록 표준 Windows <xref:System.Windows.Forms.OpenFileDialog> 대화 상자가 열립니다.  웨이브 파일을 선택하면 winmm.DLL 어셈블리의 `PlaySound()` 메서드를 통해 파일이 재생됩니다.  winmm.dll의 `PlaySound` 메서드에 대한 자세한 내용은 [Using the PlaySound function with Waveform\-Audio Files](http://go.microsoft.com/fwlink/?LinkId=148553)를 참조하십시오.  확장명이 .wav인 파일을 찾아 선택한 다음 **열기**를 클릭하여 웨이브 파일을 플랫폼 호출을 통해 재생합니다.  선택한 파일의 전체 경로가 텍스트 상자에 표시됩니다.  
  
 **파일 열기** 대화 상자는 확장명이 .wav인 파일만 표시하기 위해 다음과 같은 필터 설정을 사용하여 필터링됩니다.  
  
 [!code-cs[csProgGuideInterop#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_1.cs)]  
  
 [!code-cs[csProgGuideInterop#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_2.cs)]  
  
## 코드 컴파일  
  
### 코드를 컴파일하려면  
  
1.  Visual Studio에서 새 C\# Windows 응용 프로그램 프로젝트를 만들고 이름을 WinSound로 지정합니다.  
  
2.  위 코드를 복사하여 `Form1.cs` 파일의 내용에 붙여넣습니다.  
  
3.  다음 코드를 복사하여 `Form1.Designer.cs` 파일의 `InitializeComponent()` 메서드에서 기존 코드 뒤에 붙여넣습니다.  
  
     [!code-cs[csProgGuideInterop#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_3.cs)]  
  
4.  코드를 컴파일하고 실행합니다.  
  
## .NET Framework 보안  
 자세한 내용은 [.NET Framework Security](http://go.microsoft.com/fwlink/?LinkId=37122)를 참조하십시오.  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [상호 운용성 개요](../../../csharp/programming-guide/interop/interoperability-overview.md)   
 [상호 운용성 개요](../../../csharp/programming-guide/interop/interoperability-overview.md)   
 [A Closer Look at Platform Invoke](http://msdn.microsoft.com/ko-kr/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243)   
 [플랫폼 호출을 사용하여 데이터 마샬링](../Topic/Marshaling%20Data%20with%20Platform%20Invoke.md)