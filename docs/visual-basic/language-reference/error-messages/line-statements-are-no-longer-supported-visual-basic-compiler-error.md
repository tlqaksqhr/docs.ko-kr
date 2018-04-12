---
title: '&#39; 줄 &#39; 문은 더 이상 지원 (Visual Basic 컴파일러 오류)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30830
- vbc30830
helpviewer_keywords:
- BC30830
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9d2db5dc786749360dfcf6789f12b5659d5713fc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="39line39-statements-are-no-longer-supported-visual-basic-compiler-error"></a>&#39; 줄 &#39; 문은 더 이상 지원 (Visual Basic 컴파일러 오류)
줄으로 된 문이 이상 지원 되지 않습니다. 파일 I/O 기능은 `Microsoft.VisualBasic.FileSystem.LineInput` 그래픽 기능으로 서 제공 `System.Drawing.Graphics.DrawLine`합니다.  
  
 **오류 ID:** BC30830  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  파일 액세스를 수행 하는 경우 사용 하 여 `Microsoft.VisualBasic.FileSystem.LineInput`합니다.  
  
2.  그래픽을 수행 하는 경우 사용 하 여 `System.Drawing.Graphics.Drawline`합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.IO>  
 <xref:System.Drawing>  
 [Visual Basic을 사용한 파일 액세스](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)
