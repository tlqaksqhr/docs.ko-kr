---
title: "방법: 이미지 메타데이터 읽기 | Microsoft Docs"
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
  - "메타데이터, 속성 항목"
  - "메타데이터, 이미지 읽기"
ms.assetid: 72ec0b31-0be7-444a-9575-1dbcb864e0be
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# 방법: 이미지 메타데이터 읽기
일부 이미지 파일에는 이미지의 특성을 확인하는 데 사용할 수 있는 메타데이터가 있습니다.  예를 들어, 디지털 사진에 포함된 메타데이터를 분석하면 사진 촬영에 사용한 카메라의 제조업체와 모델을 알 수 있습니다.  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에서는 기존 메타데이터를 읽을 수 있을 뿐 아니라 이미지 파일에 새 메타데이터를 쓸 수도 있습니다.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에서는 개별 메타데이터 부분을 <xref:System.Drawing.Imaging.PropertyItem> 개체에 저장합니다.  <xref:System.Drawing.Image> 개체의 <xref:System.Drawing.Image.PropertyItems%2A> 속성을 읽어 파일에 있는 모든 메타데이터를 검색할 수 있습니다.  <xref:System.Drawing.Image.PropertyItems%2A> 속성은 <xref:System.Drawing.Imaging.PropertyItem> 개체 배열을 반환합니다.  
  
 <xref:System.Drawing.Imaging.PropertyItem> 개체에는 `Id`, `Value`, `Len` 및 `Type`이라는 네 가지 속성이 있습니다.  
  
## Id  
 메타데이터 항목을 식별하는 태그입니다.  <xref:System.Drawing.Imaging.PropertyItem.Id%2A>에 할당할 수 있는 값 중 일부가 다음 표에 나와 있습니다.  
  
|16진수 값|설명|  
|------------|--------|  
|0x0320<br /><br /> 0x010F<br /><br /> 0x0110<br /><br /> 0x9003<br /><br /> 0x829A<br /><br /> 0x5090<br /><br /> 0x5091|이미지 타이틀<br /><br /> 장비 제조업체<br /><br /> 장비 모델<br /><br /> ExifDTOriginal<br /><br /> Exif 노출 시간<br /><br /> 광도 테이블<br /><br /> 색소 테이블|  
  
## 값  
 값 배열입니다.  값의 형식은 <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 속성에 따라 결정됩니다.  
  
## Len  
 <xref:System.Drawing.Imaging.PropertyItem.Value%2A> 속성이 가리키는 값 배열의 바이트 단위 길이입니다.  
  
## 형식  
 `Value` 속성이 가리키는 배열에 있는 값의 데이터 형식입니다.  `Type` 속성 값이 나타내는 형식이 다음 표에 나와 있습니다.  
  
|숫자 값|설명|  
|----------|--------|  
|1|`Byte`입니다.|  
|2|ASCII로 인코딩된 `Byte` 개체의 배열입니다.|  
|3|16비트 정수입니다.|  
|4|32비트 정수입니다.|  
|5|유리수를 나타내는 `Byte` 개체 두 개로 이루어진 배열입니다.|  
|6|사용되지 않습니다.|  
|7|정의되어 있지 않습니다.|  
|8|사용되지 않습니다.|  
|9|`SLong`|  
|10|`SRational`|  
  
## 예제  
  
### 설명  
 다음 코드 예제에서는 `FakePhoto.jpg` 파일에 있는 일곱 가지 메타데이터를 읽고 화면에 표시합니다.  목록에서 두 번째\(인덱스 1\) 속성 항목의 <xref:System.Drawing.Imaging.PropertyItem.Id%2A>는 0x010F\(장비 제조업체\)이고 <xref:System.Drawing.Imaging.PropertyItem.Type%2A>은 2\(ASCII로 인코딩된 바이트 배열\)입니다.  코드 예제에서는 해당 속성 항목의 값을 표시합니다.  
  
 코드를 실행하면 아래와 비슷한 결과가 나타납니다.  
  
 `Property Item 0`  
  
 `id: 0x320`  
  
 `type: 2`  
  
 `length: 16 bytes`  
  
 `Property Item 1`  
  
 `id: 0x10f`  
  
 `type: 2`  
  
 `length: 17 bytes`  
  
 `Property Item 2`  
  
 `id: 0x110`  
  
 `type: 2`  
  
 `length: 7 bytes`  
  
 `Property Item 3`  
  
 `id: 0x9003`  
  
 `type: 2`  
  
 `length: 20 bytes`  
  
 `Property Item 4`  
  
 `id: 0x829a`  
  
 `type: 5`  
  
 `length: 8 bytes`  
  
 `Property Item 5`  
  
 `id: 0x5090`  
  
 `type: 3`  
  
 `length: 128 bytes`  
  
 `Property Item 6`  
  
 `id: 0x5091`  
  
 `type: 3`  
  
 `length: 128 bytes`  
  
 `The equipment make is Northwind Camera.`  
  
### 코드  
 [!code-csharp[System.Drawing.WorkingWithImages#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.WorkingWithImages#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]  
  
## 코드 컴파일  
 앞의 예제는 Windows Forms에서 사용해야 하며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`를 필요로 합니다.  폼의 <xref:System.Windows.Forms.Control.Paint> 이벤트를 처리하고 이 코드를 그리기 이벤트 처리기에 붙여 넣습니다.  `FakePhoto.jpg`를 시스템에서 사용할 수 있는 이미지 이름 및 경로로 바꾸고 `System.Drawing.Imaging` 네임스페이스를 가져와야 합니다.  
  
## 참고 항목  
 [이미지, 비트맵 및 메타파일](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)   
 [이미지, 비트맵, 아이콘 및 메타파일 사용](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)