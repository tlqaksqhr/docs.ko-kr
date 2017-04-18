---
title: "방법: 파일 대화 상자에 사용자 지정 위치 추가 | Microsoft Docs"
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
  - "대화 상자에 사용자 지정 위치"
  - "대화 상자에 사용자 지정 위치 추가"
  - "CustomPlaces 컬렉션"
ms.assetid: 63f6469b-59cd-40f6-9e61-8b5831856780
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: 파일 대화 상자에 사용자 지정 위치 추가
기본 열기 및 저장 대화 상자에 [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] 영역이 라는 제목의 대화 상자의 왼쪽에 있는 **즐겨찾기 링크**합니다. 이 영역에는 사용자 지정 위치 라고 합니다. <xref:System.Windows.Forms.OpenFileDialog> 및 <xref:System.Windows.Forms.SaveFileDialog> 클래스를 사용 하면 폴더를 추가 하는 <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> 컬렉션입니다.  
  
> [!NOTE]
>  에 표시 하는 사용자 지정 위치에 대 한 순서는 <xref:System.Windows.Forms.OpenFileDialog> 또는 <xref:System.Windows.Forms.SaveFileDialog>, <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> 속성으로 설정 되어 있어야 `true` (기본값).  
  
### <a name="to-add-a-custom-place-to-a-file-dialog-box"></a>파일 대화 상자에는 사용자 지정 위치를 추가 하려면  
  
-   알려진 폴더 GUID 경로 추가 또는 <xref:System.Windows.Forms.FileDialogCustomPlace> 개체는 <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> 컬렉션 대화 상자입니다.  
  
     다음 코드 예제에는 경로 추가 하는 방법을 보여 줍니다.  
  
    ```vb  
    OpenFileDialog1.CustomPlaces.Add("C:\MyCustomPlace")  
    ```  
  
    ```csharp  
    openFileDialog1.CustomPlaces.Add("C:\\MyCustomPlace");  
    ```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.FileDialog>   
 <xref:System.Windows.Forms.FileDialogCustomPlacesCollection.Add%2A?displayProperty=fullName>   
 [파일 대화 상자의 사용자 지정 위치에 대 한 알려진 폴더 Guid](../../../../docs/framework/winforms/controls/known-folder-guids-for-file-dialog-custom-places.md)