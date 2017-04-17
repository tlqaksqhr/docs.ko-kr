---
title: "방법: Windows Form에서 리소스에 포함된 소리 재생 | Microsoft Docs"
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
  - "소리를 리소스에서 재생"
  - "소리 재생 되는 리소스 [Windows Forms]"
  - "리소스에서 소리 재생"
  - "SoundPlayer 클래스, 리소스에서 소리 재생"
ms.assetid: 7d148bb6-8a1e-47d7-a08d-35828d2e688f
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# 방법: Windows Form에서 리소스에 포함된 소리 재생
사용할 수는 <xref:System.Media.SoundPlayer> 포함된 리소스에서 소리를 재생 하는 클래스입니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[System.Windows.Forms.Sound#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Sound/CS/soundtestform.cs#10)]
 [!code-vb[System.Windows.Forms.Sound#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Sound/VB/soundtestform.vb#10)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
 가져오기는 <xref:System.Media?displayProperty=fullName> 네임 스페이스입니다.  
  
 프로젝트에 포함 리소스로 사운드 파일을 포함 합니다.  
  
 대체 "<>\>" 사운드 파일이 포함 된 어셈블리의 이름입니다. ".Dll" 접미사를 포함 하지 마십시오.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Media.SoundPlayer>   
 [방법: Windows Form에서 소리 재생](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)   
 [방법: Windows Form에서 소리 재생 반복](../../../../docs/framework/winforms/controls/how-to-loop-a-sound-playing-on-a-windows-form.md)