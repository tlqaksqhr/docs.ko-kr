---
title: "방법: Windows Forms ProgressBar 컨트롤에서 표시하는 값 설정 | Microsoft Docs"
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
  - "Increment 메서드"
  - "PerformStep 메서드"
  - "Progress 컨트롤, 표시되는 값 설정"
  - "ProgressBar 컨트롤[Windows Forms], 표시되는 값 설정"
  - "Step 속성"
  - "Value 속성"
ms.assetid: 0e5010ad-1e9a-4271-895e-5a3d24d37a26
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: Windows Forms ProgressBar 컨트롤에서 표시하는 값 설정
> [!IMPORTANT]
>  <xref:System.Windows.Forms.ToolStripProgressBar> 컨트롤은 <xref:System.Windows.Forms.ProgressBar> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.ProgressBar> 컨트롤을 계속 유지하도록 선택할 수 있습니다.  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]에서는 지정한 값을 <xref:System.Windows.Forms.ProgressBar> 컨트롤에 표시하기 위한 다음과 같은 여러 가지 방법을 제공합니다.  진행 중인 작업이나 해결하려는 문제에 따라 적절한 방법을 선택할 수 있습니다.  다음 표에서는 선택할 수 있는 방법을 설명합니다.  
  
|방법|설명|  
|--------|--------|  
|<xref:System.Windows.Forms.ProgressBar> 컨트롤의 값을 직접 설정합니다.|이 방법은 데이터 소스에서 레코드를 읽을 때와 같이 관련된 항목의 총 개수를 알고 있는 작업에 유용합니다.  뿐만 아니라 값을 한두 번만 설정하려는 경우에도 이 방법을 이용하면 쉽습니다.  그리고 진행률 표시줄에 표시되는 값을 감소시키려는 경우에도 이 방법을 사용합니다.|  
|<xref:System.Windows.Forms.ProgressBar>에 표시되는 값을 고정된 값만큼 증가시킵니다.|이 방법은 경과 시간이나 알려진 총 파일 개수 중 처리된 파일 개수 등과 같이 최소값과 최대값 사이의 단순한 개수를 표시하려는 경우 유용합니다.|  
|<xref:System.Windows.Forms.ProgressBar>에 표시되는 값을 일정하지 않은 값만큼 증가시킵니다.|이 방법은 표시되는 값을 일정하지 않은 값으로 여러 번 변경하려는 경우 유용합니다.  디스크에 일련의 파일을 쓰는 동안 사용되는 하드 디스크 공간을 표시하려는 경우를 예로 들 수 있습니다.|  
  
 진행률 표시줄에 표시되는 값을 설정하는 가장 직접적인 방법은 <xref:System.Windows.Forms.ProgressBar.Value%2A> 속성을 설정하는 것입니다.  이 작업은 디자인 타임 또는 런타임에 할 수 있습니다.  
  
### ProgressBar 값을 직접 설정하려면  
  
1.  <xref:System.Windows.Forms.ProgressBar> 컨트롤의 <xref:System.Windows.Forms.ProgressBar.Minimum%2A> 및 <xref:System.Windows.Forms.ProgressBar.Maximum%2A> 값을 설정합니다.  
  
2.  코드에서 컨트롤의 <xref:System.Windows.Forms.ProgressBar.Value%2A> 속성을 앞에서 설정한 최소값과 최대값 사이의 정수 값으로 설정합니다.  
  
    > [!NOTE]
    >  <xref:System.Windows.Forms.ProgressBar.Minimum%2A> 및 <xref:System.Windows.Forms.ProgressBar.Maximum%2A> 속성으로 설정된 범위를 벗어난 값으로 <xref:System.Windows.Forms.ProgressBar.Value%2A> 속성을 설정하면 컨트롤에서 <xref:System.ArgumentException> 예외를 throw합니다.  
  
     다음 코드 예제에서는 <xref:System.Windows.Forms.ProgressBar> 값을 직접 설정하는 방법을 보여 줍니다.  이 코드는 데이터 소스에서 레코드를 읽고, 데이터 레코드를 읽을 때마다 진행률 표시줄과 레이블을 업데이트합니다.  이 예제에서는 폼에 <xref:System.Windows.Forms.Label> 컨트롤과 <xref:System.Windows.Forms.ProgressBar> 컨트롤이 있고 `FirstName`  및 `Last Name`  필드가 포함된 `CustomerRow` 라는 행이 있는 데이터 테이블이 있어야 합니다.  
  
    ```vb  
    Public Sub CreateNewRecords()  
       ' Sets the progress bar's Maximum property to  
       ' the total number of records to be created.  
       ProgressBar1.Maximum = 20  
  
       ' Creates a new record in the dataset.  
       ' NOTE: The code below will not compile, it merely  
       ' illustrates how the progress bar would be used.  
       Dim anyRow As CustomerRow = DatasetName.ExistingTable.NewRow  
       anyRow.FirstName = "Stephen"  
       anyRow.LastName = "James"  
       ExistingTable.Rows.Add(anyRow)  
  
       ' Increases the value displayed by the progress bar.  
       ProgressBar1.Value += 1  
       ' Updates the label to show that a record was read.  
       Label1.Text = "Records Read = " & ProgressBar1.Value.ToString()  
    End Sub  
  
    ```  
  
    ```csharp  
    public void createNewRecords()  
    {  
       // Sets the progress bar's Maximum property to  
       // the total number of records to be created.  
       progressBar1.Maximum = 20;  
  
       // Creates a new record in the dataset.  
       // NOTE: The code below will not compile, it merely  
       // illustrates how the progress bar would be used.  
       CustomerRow anyRow = DatasetName.ExistingTable.NewRow();  
       anyRow.FirstName = "Stephen";  
       anyRow.LastName = "James";  
       ExistingTable.Rows.Add(anyRow);  
  
       // Increases the value displayed by the progress bar.  
       progressBar1.Value += 1;  
       // Updates the label to show that a record was read.  
       label1.Text = "Records Read = " + progressBar1.Value.ToString();  
    }  
    ```  
  
     고정된 간격으로 진행되는 진행률을 표시하려면 값을 설정한 다음 <xref:System.Windows.Forms.ProgressBar> 컨트롤의 값을 해당 간격으로 증가시키는 메서드를 호출합니다.  이 방법은 진행률을 전체에 대한 백분율로 측정하지 않는 타이머 및 기타 시나리오에 유용합니다.  
  
### 진행률 표시줄을 고정된 값으로 증가시키려면  
  
1.  <xref:System.Windows.Forms.ProgressBar> 컨트롤의 <xref:System.Windows.Forms.ProgressBar.Minimum%2A> 및 <xref:System.Windows.Forms.ProgressBar.Maximum%2A> 값을 설정합니다.  
  
2.  컨트롤의 <xref:System.Windows.Forms.ProgressBar.Step%2A> 속성을 진행률 표시줄에 표시되는 증가치를 나타내는 정수로 설정합니다.  
  
3.  <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> 메서드를 호출하여 <xref:System.Windows.Forms.ProgressBar.Step%2A> 속성에 설정된 값으로 표시되도록 값을 변경합니다.  
  
     다음 코드 예제에서는 진행률 표시줄이 복사 작업에 관련된 파일 개수를 관리하는 방법을 보여 줍니다.  
  
     다음 예제에서는 각 파일을 메모리로 읽어 들일 때마다 진행률 표시줄과 레이블이 업데이트되어 읽어 들인 총 파일 개수를 나타냅니다.  이 예제에서는 폼에 <xref:System.Windows.Forms.Label> 컨트롤과 <xref:System.Windows.Forms.ProgressBar> 컨트롤이 있어야 합니다.  
  
    ```vb  
    Public Sub LoadFiles()  
       ' Sets the progress bar's minimum value to a number representing  
       ' no operations complete -- in this case, no files read.  
       ProgressBar1.Minimum = 0  
       ' Sets the progress bar's maximum value to a number representing  
       ' all operations complete -- in this case, all five files read.  
       ProgressBar1.Maximum = 5  
       ' Sets the Step property to amount to increase with each iteration.  
       ' In this case, it will increase by one with every file read.  
       ProgressBar1.Step = 1  
  
       ' Dimensions a counter variable.  
       Dim i As Integer  
       ' Uses a For...Next loop to iterate through the operations to be  
       ' completed. In this case, five files are to be copied into memory,  
       ' so the loop will execute 5 times.  
       For i = 0 To 4  
          ' Insert code to copy a file  
          ProgressBar1.PerformStep()  
          ' Update the label to show that a file was read.  
          Label1.Text = "# of Files Read = " & ProgressBar1.Value.ToString  
       Next i  
    End Sub  
  
    ```  
  
    ```csharp  
    public void loadFiles()  
    {  
       // Sets the progress bar's minimum value to a number representing  
       // no operations complete -- in this case, no files read.  
       progressBar1.Minimum = 0;  
       // Sets the progress bar's maximum value to a number representing  
       // all operations complete -- in this case, all five files read.  
       progressBar1.Maximum = 5;  
       // Sets the Step property to amount to increase with each iteration.  
       // In this case, it will increase by one with every file read.  
       progressBar1.Step = 1;  
  
       // Uses a for loop to iterate through the operations to be  
       // completed. In this case, five files are to be copied into memory,  
       // so the loop will execute 5 times.  
       for (int i = 0; i <= 4; i++)  
       {  
          // Inserts code to copy a file  
          progressBar1.PerformStep();  
          // Updates the label to show that a file was read.  
          label1.Text = "# of Files Read = " + progressBar1.Value.ToString();  
       }  
    }  
    ```  
  
     진행률 표시줄에 표시되는 값이 각각 고유한 간격으로 증가하도록 만들 수 있습니다.  이 방법은 크기가 다른 여러 개의 파일을 하드 디스크에 쓸 때와 같이 일련의 고유한 작업을 추적하거나 진행률을 전체에 대한 백분율로 측정하려는 경우 유용합니다.  
  
### 진행률 표시줄을 동적 값으로 증가시키려면  
  
1.  <xref:System.Windows.Forms.ProgressBar> 컨트롤의 <xref:System.Windows.Forms.ProgressBar.Minimum%2A> 및 <xref:System.Windows.Forms.ProgressBar.Maximum%2A> 값을 설정합니다.  
  
2.  <xref:System.Windows.Forms.ProgressBar.Increment%2A> 메서드를 호출하여 지정한 정수로 표시되도록 값을 변경합니다.  
  
     다음 코드 예제에서는 진행률 표시줄이 복사 작업 동안 사용된 디스크 공간을 계산하는 방법을 보여 줍니다.  
  
     다음 예제에서는 각 파일이 하드 디스크에 쓰여질 때마다 진행률 표시줄과 레이블이 업데이트되어 사용할 수 있는 하드 디스크 공간을 나타냅니다.  이 예제에서는 폼에 <xref:System.Windows.Forms.Label> 컨트롤과 <xref:System.Windows.Forms.ProgressBar> 컨트롤이 있어야 합니다.  
  
    ```vb  
    Public Sub ReadFiles()  
       ' Sets the progress bar's minimum value to a number   
       ' representing the hard disk space before the files are read in.  
       ' You will most likely have to set this using a system call.  
       ' NOTE: The code below is meant to be an example and  
       ' will not compile.  
       ProgressBar1.Minimum = AvailableDiskSpace()  
       ' Sets the progress bar's maximum value to a number   
       ' representing the total hard disk space.  
       ' You will most likely have to set this using a system call.  
       ' NOTE: The code below is meant to be an example   
       ' and will not compile.  
       ProgressBar1.Maximum = TotalDiskSpace()  
  
       ' Dimension a counter variable.  
       Dim i As Integer  
       ' Uses a For...Next loop to iterate through the operations to be  
       ' completed. In this case, five files are to be written to the disk,  
       ' so it will execute the loop 5 times.  
       For i = 1 To 5  
          ' Insert code to read a file into memory and update file size.  
          ' Increases the progress bar's value based on the size of   
          ' the file currently being written.  
          ProgressBar1.Increment(FileSize)  
          ' Updates the label to show available drive space.  
          Label1.Text = "Current Disk Space Used = " &_   
          ProgressBar1.Value.ToString()  
       Next i  
    End Sub  
  
    ```  
  
    ```csharp  
    public void readFiles()  
    {  
       // Sets the progress bar's minimum value to a number   
       // representing the hard disk space before the files are read in.  
       // You will most likely have to set this using a system call.  
       // NOTE: The code below is meant to be an example and   
       // will not compile.  
       progressBar1.Minimum = AvailableDiskSpace();  
       // Sets the progress bar's maximum value to a number   
       // representing the total hard disk space.  
       // You will most likely have to set this using a system call.  
       // NOTE: The code below is meant to be an example   
       // and will not compile.  
       progressBar1.Maximum = TotalDiskSpace();  
  
       // Uses a for loop to iterate through the operations to be  
       // completed. In this case, five files are to be written  
       // to the disk, so it will execute the loop 5 times.  
       for (int i = 1; i<= 5; i++)  
       {  
          // Insert code to read a file into memory and update file size.  
          // Increases the progress bar's value based on the size of   
          // the file currently being written.  
          progressBar1.Increment(FileSize);  
          // Updates the label to show available drive space.  
          label1.Text = "Current Disk Space Used = " + progressBar1.Value.ToString();  
       }  
    }  
    ```  
  
## 참고 항목  
 <xref:System.Windows.Forms.ProgressBar>   
 <xref:System.Windows.Forms.ToolStripProgressBar>   
 [ProgressBar 컨트롤 개요](../../../../docs/framework/winforms/controls/progressbar-control-overview-windows-forms.md)   
 [ProgressBar 컨트롤](../../../../docs/framework/winforms/controls/progressbar-control-windows-forms.md)