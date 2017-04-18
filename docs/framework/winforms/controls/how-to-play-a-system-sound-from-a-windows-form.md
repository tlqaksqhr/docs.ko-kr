---
title: "방법: Windows Form에서 시스템 소리 재생 | Microsoft Docs"
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
  - "소리를 시스템 이벤트에 대해 재생"
  - "소리 재생, Windows Forms"
  - "시스템 소리를 Windows Forms에서 재생"
  - "시스템 소리 재생"
  - "시스템 소리 SoundPlayer 클래스"
  - "소리 재생"
  - "소리 예제 [Windows Forms]"
ms.assetid: afb206ff-4824-4804-a8d4-185bf5ad8e7c
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: Windows Form에서 시스템 소리 재생
다음 코드 예제에서는 재생은 `Exclamation` 런타임에 시스템 소리입니다. 시스템 소리에 대 한 자세한 내용은 참조 <xref:System.Media.SystemSounds>합니다.  
  
## <a name="example"></a>예제  
  
```vb  
Public Sub PlayExclamation()  
    SystemSounds.Exclamation.Play()  
End Sub  
  
```  
  
```csharp  
public void playExclamation()  
{  
    SystemSounds.Exclamation.Play();  
}  
```  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   에 대 한 참조는 <xref:System.Media?displayProperty=fullName> 네임 스페이스입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Media.SoundPlayer>   
 <xref:System.Media.SystemSounds>   
 [방법: Windows Form에서 경고음 재생](../../../../docs/framework/winforms/controls/how-to-play-a-beep-from-a-windows-form.md)   
 [방법: Windows Form에서 소리 재생](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)