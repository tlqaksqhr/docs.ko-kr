---
title: "방법: Windows Form에서 경고음 재생 | Microsoft Docs"
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
  - "소리, 경고음"
  - "Windows Forms, 소리"
  - "소리 재생"
  - "폼, 소리"
  - "소리 예제 [Windows Forms]"
ms.assetid: 7ea5cded-4888-4f35-8f28-5cab1a55c973
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# 방법: Windows Form에서 경고음 재생
이 예제에서는 런타임에 경고음을 재생 합니다.  
  
## <a name="example"></a>예제  
  
```vb  
Public Sub OnePing()  
    Beep()  
End Sub  
```  
  
```csharp  
public void onePing()  
{  
    SystemSounds.Beep.Play();  
}  
```  
  
> [!NOTE]
>  C# 코드 샘플에서 재생 되는 소리에 의해 결정 됩니다는 <xref:System.Media.SystemSounds.Beep%2A> 시스템 소리 설정 합니다. 자세한 내용은 참조 <xref:System.Media.SystemSounds>합니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에 대 한 참조를 C#의 경우는 <xref:System.Media?displayProperty=fullName> 네임 스페이스입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.Interaction.Beep%2A>   
 <xref:System.Media.SoundPlayer>   
 [방법: Windows Form에서 시스템 소리 재생](../../../../docs/framework/winforms/controls/how-to-play-a-system-sound-from-a-windows-form.md)   
 [방법: Windows Form에서 소리 재생](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)