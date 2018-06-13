---
title: '방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤에서 항목 추가 및 제거'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- combo boxes [Windows Forms], adding items
- list boxes [Windows Forms], removing items
- ComboBox control [Windows Forms], adding and removing items
- ListBox control [Windows Forms], adding and removing items
- list boxes [Windows Forms], adding items
- combo boxes [Windows Forms], removing items
- CheckedListBox control [Windows Forms], adding and removing items
ms.assetid: 7224c8d2-4118-443e-ae1e-d7c17d1e69ee
ms.openlocfilehash: f9319ffe5e9c4f06565648565ce21dec6fc672f9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527189"
---
# <a name="how-to-add-and-remove-items-from-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="6645f-102">방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤에서 항목 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="6645f-102">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>
<span data-ttu-id="6645f-103">항목 목록 상자에서 Windows Forms 콤보 상자에 추가할 수 또는 이러한 컨트롤을 다양 한 데이터 원본에 바인딩될 수 때문에 다양 한 방식으로 목록 상자를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6645f-103">Items can be added to a Windows Forms combo box, list box, or checked list box in a variety of ways, because these controls can be bound to a variety of data sources.</span></span> <span data-ttu-id="6645f-104">그러나이 항목은 가장 간단한 방법을 보여 줍니다 이루어지며 데이터 바인딩이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6645f-104">However, this topic demonstrates the simplest method and requires no data binding.</span></span> <span data-ttu-id="6645f-105">표시 되는 항목은 일반적으로 문자열입니다. 그러나 모든 개체를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6645f-105">The items displayed are usually strings; however, any object can be used.</span></span> <span data-ttu-id="6645f-106">컨트롤에 표시 되는 텍스트 개체의 반환 값은 `ToString` 메서드.</span><span class="sxs-lookup"><span data-stu-id="6645f-106">The text that is displayed in the control is the value returned by the object's `ToString` method.</span></span>  
  
### <a name="to-add-items"></a><span data-ttu-id="6645f-107">항목을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="6645f-107">To add items</span></span>  
  
1.  <span data-ttu-id="6645f-108">목록에 문자열 또는 개체를 사용 하 여 추가 된 `Add` 의 메서드는 `ObjectCollection` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="6645f-108">Add the string or object to the list by using the `Add` method of the `ObjectCollection` class.</span></span> <span data-ttu-id="6645f-109">사용 하 여 컬렉션은 참조는 `Items` 속성:</span><span class="sxs-lookup"><span data-stu-id="6645f-109">The collection is referenced using the `Items` property:</span></span>  
  
    ```vb  
    ComboBox1.Items.Add("Tokyo")  
    ```  
  
    ```csharp  
    comboBox1.Items.Add("Tokyo");  
    ```  
  
    ```cpp  
    comboBox1->Items->Add("Tokyo");  
    ```  
  
     - <span data-ttu-id="6645f-110">또는</span><span class="sxs-lookup"><span data-stu-id="6645f-110">or -</span></span>  
  
2.  <span data-ttu-id="6645f-111">문자열 또는 개체를 사용 하 여 목록에서 원하는 지점에 삽입 된 `Insert` 메서드:</span><span class="sxs-lookup"><span data-stu-id="6645f-111">Insert the string or object at the desired point in the list with the `Insert` method:</span></span>  
  
    ```vb  
    CheckedListBox1.Items.Insert(0, "Copenhagen")  
    ```  
  
    ```csharp  
    checkedListBox1.Items.Insert(0, "Copenhagen");  
    ```  
  
    ```cpp  
    checkedListBox1->Items->Insert(0, "Copenhagen");  
    ```  
  
     - <span data-ttu-id="6645f-112">또는</span><span class="sxs-lookup"><span data-stu-id="6645f-112">or -</span></span>  
  
3.  <span data-ttu-id="6645f-113">전체 배열을 할당는 `Items` 컬렉션:</span><span class="sxs-lookup"><span data-stu-id="6645f-113">Assign an entire array to the `Items` collection:</span></span>  
  
    ```vb  
    Dim ItemObject(9) As System.Object  
    Dim i As Integer  
       For i = 0 To 9  
       ItemObject(i) = "Item" & i  
    Next i  
    ListBox1.Items.AddRange(ItemObject)  
    ```  
  
    ```csharp  
    System.Object[] ItemObject = new System.Object[10];  
    for (int i = 0; i <= 9; i++)  
    {  
       ItemObject[i] = "Item" + i;  
    }  
    listBox1.Items.AddRange(ItemObject);  
    ```  
  
    ```cpp  
    Array<System::Object^>^ ItemObject = gcnew Array<System::Object^>(10);  
    for (int i = 0; i <= 9; i++)  
    {  
       ItemObject[i] = String::Concat("Item", i.ToString());  
    }  
    listBox1->Items->AddRange(ItemObject);  
    ```  
  
### <a name="to-remove-an-item"></a><span data-ttu-id="6645f-114">항목을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="6645f-114">To remove an item</span></span>  
  
1.  <span data-ttu-id="6645f-115">호출의 `Remove` 또는 `RemoveAt` 메서드 항목을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="6645f-115">Call the `Remove` or `RemoveAt` method to delete items.</span></span>  
  
     <span data-ttu-id="6645f-116">`Remove` 제거할 항목을 지정 하는 하나의 인수가 있습니다.`RemoveAt`</span><span class="sxs-lookup"><span data-stu-id="6645f-116">`Remove` has one argument that specifies the item to remove.`RemoveAt`</span></span> <span data-ttu-id="6645f-117">지정된 된 인덱스 번호를 가진 항목을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6645f-117">removes the item with the specified index number.</span></span>  
  
    ```vb  
    ' To remove item with index 0:  
    ComboBox1.Items.RemoveAt(0)  
    ' To remove currently selected item:  
    ComboBox1.Items.Remove(ComboBox1.SelectedItem)  
    ' To remove "Tokyo" item:  
    ComboBox1.Items.Remove("Tokyo")  
    ```  
  
    ```csharp  
    // To remove item with index 0:  
    comboBox1.Items.RemoveAt(0);  
    // To remove currently selected item:  
    comboBox1.Items.Remove(comboBox1.SelectedItem);  
    // To remove "Tokyo" item:  
    comboBox1.Items.Remove("Tokyo");  
    ```  
  
    ```cpp  
    // To remove item with index 0:  
    comboBox1->Items->RemoveAt(0);  
    // To remove currently selected item:  
    comboBox1->Items->Remove(comboBox1->SelectedItem);  
    // To remove "Tokyo" item:  
    comboBox1->Items->Remove("Tokyo");  
    ```  
  
### <a name="to-remove-all-items"></a><span data-ttu-id="6645f-118">모든 항목을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="6645f-118">To remove all items</span></span>  
  
1.  <span data-ttu-id="6645f-119">호출 된 `Clear` 메서드 컬렉션에서 모든 항목을 제거 하려면:</span><span class="sxs-lookup"><span data-stu-id="6645f-119">Call the `Clear` method to remove all items from the collection:</span></span>  
  
    ```vb  
    ListBox1.Items.Clear()  
    ```  
  
    ```csharp  
    listBox1.Items.Clear();  
    ```  
  
    ```cpp  
    listBox1->Items->Clear();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6645f-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6645f-120">See Also</span></span>  
 <xref:System.Windows.Forms.ComboBox>  
 <xref:System.Windows.Forms.ListBox>  
 <xref:System.Windows.Forms.CheckedListBox>  
 [<span data-ttu-id="6645f-121">방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤의 내용 정렬</span><span class="sxs-lookup"><span data-stu-id="6645f-121">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)  
 [<span data-ttu-id="6645f-122">ListBox 대신 Windows Forms ComboBox를 사용해야 하는 경우</span><span class="sxs-lookup"><span data-stu-id="6645f-122">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)  
 [<span data-ttu-id="6645f-123">옵션 목록 표시에 사용된 Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="6645f-123">Windows Forms Controls Used to List Options</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)
