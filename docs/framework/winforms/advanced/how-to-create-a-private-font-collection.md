---
title: "방법: 개인 글꼴 컬렉션 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "글꼴, 개인 컬렉션 만들기"
  - "개인 글꼴 컬렉션, 만들기"
ms.assetid: 6533d5e5-a8dc-4b76-9fc4-3bf75c8b9212
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# 방법: 개인 글꼴 컬렉션 만들기
<xref:System.Drawing.Text.PrivateFontCollection> 클래스는 <xref:System.Drawing.Text.FontCollection> 추상 기본 클래스에서 상속됩니다.  <xref:System.Drawing.Text.PrivateFontCollection> 개체를 사용하여 응용 프로그램용 글꼴 집합을 유지 관리할 수 있습니다.  설치되어 있는 시스템 글꼴 뿐 아니라 컴퓨터에 설치되어 있지 않은 글꼴도 개인 글꼴 컬렉션에 포함할 수 있습니다.  글꼴 파일을 개인 글꼴 컬렉션에 추가하려면 <xref:System.Drawing.Text.PrivateFontCollection> 개체의 <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile%2A> 메서드를 호출하십시오.  
  
 <xref:System.Drawing.Text.PrivateFontCollection> 개체의 <xref:System.Drawing.Text.FontCollection.Families%2A> 속성은 <xref:System.Drawing.FontFamily> 개체의 배열을 포함합니다.  
  
 개인 글꼴 컬렉션에 있는 글꼴 패밀리의 수는 컬렉션에 추가된 글꼴 파일의 수와 다를 수도 있습니다.  예를 들어, ArialBd.tff, Times.tff 및 TimesBd.tff 파일을 컬렉션에 추가할 경우  파일은 세 개지만 Times.tff와 TimesBd.tff가 같은 패밀리에 속하기 때문에 컬렉션에는 두 개의 패밀리만 나타납니다.  
  
## 예제  
 다음 예제에서는 아래와 같은 세 개의 글꼴 파일을 <xref:System.Drawing.Text.PrivateFontCollection> 개체에 추가합니다.  
  
-   C:\\*systemroot*\\Fonts\\Arial.tff\(Arial, 보통\)  
  
-   C:\\*systemroot*\\Fonts\\CourBI.tff\(Courier New, 굵은 기울임꼴\)  
  
-   C:\\*systemroot*\\Fonts\\TimesBd.tff\(Times New Roman, 굵게\)  
  
 이 코드는 <xref:System.Drawing.Text.PrivateFontCollection> 개체의 <xref:System.Drawing.Text.FontCollection.Families%2A> 속성에서 <xref:System.Drawing.FontFamily> 개체의 배열을 가져옵니다.  
  
 이 코드는 컬렉션의 각 <xref:System.Drawing.FontFamily> 개체에 대해 <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> 메서드를 호출하여 보통, 굵게, 기울임꼴, 굵은 기울임꼴, 밑줄 및 취소선 같은 다양한 스타일을 사용할 수 있는지 여부를 확인합니다.  <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> 메서드에 전달되는 인수는 <xref:System.Drawing.FontStyle> 열거형의 멤버입니다.  
  
 특정 패밀리\/스타일 조합을 사용할 수 있는 경우 해당 패밀리와 스타일을 사용하여 <xref:System.Drawing.Font> 개체가 만들어집니다.  <xref:System.Drawing.Font.%23ctor%2A> 생성자의 다른 변형에서는 <xref:System.Drawing.FontFamily> 개체가 첫 번째 인수로 지정되지만 이 <xref:System.Drawing.Font.%23ctor%2A> 생성자에는 글꼴 패밀리 이름이 첫 번째 인수로 전달됩니다.  <xref:System.Drawing.Font> 개체가 만들어지면 이 개체가 <xref:System.Drawing.Graphics> 클래스의 <xref:System.Drawing.Graphics.DrawString%2A> 메서드에 전달되어 패밀리 이름과 스타일 이름을 표시합니다.  
  
 다음 코드를 실행하면 아래 그림과 비슷한 결과가 나타납니다.  
  
 ![글꼴 텍스트](../../../../docs/framework/winforms/advanced/media/csfontstext7.png "csfontstext7")  
  
 다음 코드 예제에서 개인 글꼴 컬렉션에 추가한 Arial.tff는 Arial 보통 스타일용 글꼴 파일입니다.  그러나 프로그램 출력을 보면 Arial 글꼴 패밀리에 대해 사용할 수 있는 스타일이 보통 외에도 여러 개가 있음을 알 수 있습니다.  이는 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에서 보통 스타일을 사용하여 굵게, 기울임꼴 및 굵은 기울임꼴 스타일을 시뮬레이션할 수 있기 때문입니다.  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에서는 보통 스타일을 사용하여 밑줄과 취소선 스타일도 만들 수 있습니다.  
  
 이와 마찬가지로 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에서는 굵게 또는 기울임꼴 스타일을 사용하여 굵은 기울임꼴 스타일을 시뮬레이션할 수 있습니다.  따라서 컬렉션에 추가한 Times 패밀리 파일은 TimesBd.tff\(Times New Roman, 굵게\)뿐이지만 프로그램 출력에는 Times 패밀리에 대해 굵은 기울임꼴 스타일도 사용할 수 있는 것으로 나타납니다.  
  
 [!code-csharp[System.Drawing.FontsAndText#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.FontsAndText#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#51)]  
  
## 코드 컴파일  
 앞의 예제는 Windows Forms에서 사용해야 하며 <xref:System.Windows.Forms.PaintEventHandler>의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`를 필요로 합니다.  
  
## 참고 항목  
 <xref:System.Drawing.Text.PrivateFontCollection>   
 [글꼴 및 텍스트 사용](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)