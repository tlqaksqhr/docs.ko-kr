---
title: "방법: Windows Form에서 소리 재생 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "소리 재생, Windows Forms"
  - "소리 재생"
  - "SoundPlayer 클래스"
  - "소리"
  - "My.Computer.Audio 개체, 소리 재생"
  - "소리 예제 [Windows Forms]"
ms.assetid: 3d3350b7-1ebd-4e05-a738-48ca1160a19d
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# 방법: Windows Form에서 소리 재생
이 예제에서는 런타임에 지정된 된 경로에서 소리를 재생 합니다.  
  
## <a name="example"></a>예제  
  
```vb  
Sub PlaySimpleSound()  
    My.Computer.Audio.Play("c:\Windows\Media\chimes.wav")  
End Sub  
```  
  
```csharp  
private void playSimpleSound()  
{  
    SoundPlayer simpleSound = new SoundPlayer(@"c:\Windows\Media\chimes.wav");  
    simpleSound.Play();  
}  
```  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   파일 이름 `"c:\Windows\Media\chimes.wav"`를 유효한 파일 이름으로 바꿉니다.  
  
-   (C#) 에 대 한 참조는 <xref:System.Media?displayProperty=fullName> 네임 스페이스입니다.  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 적절 한 구조적된 예외 처리 블록 내에서 파일 작업을 묶어야 합니다.  
  
 다음 조건에서 예외가 발생합니다.  
  
-   경로 이름 형식이 잘못되었습니다. 잘못 된 문자를 포함 하거나 공백만 예를 들어 (<xref:System.ArgumentException> 클래스).  
  
-   경로가 읽기 전용 (<xref:System.IO.IOException> 클래스).  
  
-   경로 이름 형식이 `null` (<xref:System.ArgumentNullException> 클래스).  
  
-   경로 이름이 너무 깁니다 (<xref:System.IO.PathTooLongException> 클래스).  
  
-   경로가 유효 하지 않거나 (<xref:System.IO.DirectoryNotFoundException> 클래스).  
  
-   경로가 콜론 ":" (<xref:System.NotSupportedException> 클래스).  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 파일 이름을 바탕으로 파일 내용을 판단하면 안 됩니다. 예를 들어 `Form1.vb` 파일이 Visual Basic 소스 파일이 아닐 수도 있습니다. 응용 프로그램에서 데이터를 사용하기 전에 모든 입력을 확인해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Media.SoundPlayer>   
 [방법: Windows Form에서 비동기적으로 소리 로드](../../../../docs/framework/winforms/controls/how-to-load-a-sound-asynchronously-within-a-windows-form.md)   
 