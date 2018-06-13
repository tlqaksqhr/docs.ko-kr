---
title: '방법: Windows Forms의 그래픽 인쇄'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], printing
- printing [Windows Forms], graphics
ms.assetid: 32b891e6-52ff-4fea-a9ff-2ce5db20a4c6
ms.openlocfilehash: 8281e1e0a3d350c3b81e26bbe59c098536ef064e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521500"
---
# <a name="how-to-print-graphics-in-windows-forms"></a><span data-ttu-id="11859-102">방법: Windows Forms의 그래픽 인쇄</span><span class="sxs-lookup"><span data-stu-id="11859-102">How to: Print Graphics in Windows Forms</span></span>
<span data-ttu-id="11859-103">대부분의 경우 Windows 기반 응용 프로그램의 그래픽 인쇄 합니다.</span><span class="sxs-lookup"><span data-stu-id="11859-103">Frequently, you will want to print graphics in your Windows-based application.</span></span> <span data-ttu-id="11859-104"><xref:System.Drawing.Graphics> 클래스는 화면이 나 프린터와 같은 장치에 개체를 그리기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="11859-104">The <xref:System.Drawing.Graphics> class provides methods for drawing objects to a device, such as a screen or printer.</span></span>  
  
### <a name="to-print-graphics"></a><span data-ttu-id="11859-105">그래픽을 인쇄 하려면</span><span class="sxs-lookup"><span data-stu-id="11859-105">To print graphics</span></span>  
  
1.  <span data-ttu-id="11859-106">추가 <xref:System.Drawing.Printing.PrintDocument> 폼 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="11859-106">Add a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2.  <span data-ttu-id="11859-107">에 <xref:System.Drawing.Printing.PrintDocument.PrintPage> 이벤트 처리기를 사용 하 여는 <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> 속성은 <xref:System.Drawing.Printing.PrintPageEventArgs> 프린터에 인쇄 하는 그래픽 종류에 지시 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="11859-107">In the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler, use the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class to instruct the printer on what kind of graphics to print.</span></span>  
  
     <span data-ttu-id="11859-108">다음 코드 예제를 경계 사각형 내의 파란색 타원을 만드는 데 사용 하는 이벤트 처리기를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="11859-108">The following code example shows an event handler used to create a blue ellipse within a bounding rectangle.</span></span> <span data-ttu-id="11859-109">사각형에는 다음 위치 차원을: 100부터 250의 너비와 높이 250 150입니다.</span><span class="sxs-lookup"><span data-stu-id="11859-109">The rectangle has the following location and dimensions: beginning at 100, 150 with a width of 250 and a height of 250.</span></span>  
  
    ```vb  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillEllipse(Brushes.Blue, New Rectangle(100, 150, 250, 250))  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_PrintPage(object sender,   
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Blue,   
         new Rectangle(100, 150, 250, 250));  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Blue,  
             Rectangle(100, 150, 250, 250));  
       }  
    ```  
  
     <span data-ttu-id="11859-110">(Visual C# 및 [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 이벤트 처리기를 등록 하려면 폼의 생성자에 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="11859-110">(Visual C# and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
    ```  
  
    ```cpp  
    this->printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="11859-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="11859-111">See Also</span></span>  
 <xref:System.Drawing.Graphics>  
 <xref:System.Drawing.Brush>  
 [<span data-ttu-id="11859-112">Windows Forms 인쇄 지원</span><span class="sxs-lookup"><span data-stu-id="11859-112">Windows Forms Print Support</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)
