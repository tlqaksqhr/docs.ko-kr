---
title: '&#39;줄&#39; 명령문은 더 이상 지원 (Visual Basic 컴파일러 오류)'
ms.date: 07/20/2015
f1_keywords:
- bc30830
- vbc30830
helpviewer_keywords:
- BC30830
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
ms.openlocfilehash: 06bba0ebfc2faec24f4720c45de3bdcfec993499
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="39line39-statements-are-no-longer-supported-visual-basic-compiler-error"></a>&#39;줄&#39; 명령문은 더 이상 지원 (Visual Basic 컴파일러 오류)
줄으로 된 문이 이상 지원 되지 않습니다. 파일 I/O 기능은 `Microsoft.VisualBasic.FileSystem.LineInput` 그래픽 기능으로 서 제공 `System.Drawing.Graphics.DrawLine`합니다.  
  
 **오류 ID:** BC30830  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  파일 액세스를 수행 하는 경우 사용 하 여 `Microsoft.VisualBasic.FileSystem.LineInput`합니다.  
  
2.  그래픽을 수행 하는 경우 사용 하 여 `System.Drawing.Graphics.Drawline`합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.IO>  
 <xref:System.Drawing>  
 [Visual Basic을 사용한 파일 액세스](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)
