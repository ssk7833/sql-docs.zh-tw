---
title: "移動方法範例 (VB) |Microsoft 文件"
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: ado
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: sql
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Move method [ADO], Visual Basic example
ms.assetid: 55eb797a-0205-40d2-a797-55b216d1d3bb
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 68061546bf86dca96d927d120a4b62f390d3dff6
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2018
---
# <a name="move-method-example-vb"></a>Move 方法範例 (VB)
這個範例會使用[移動](../../../ado/reference/ado-api/move-method-ado.md)來定位資料錄指標的方法會根據使用者輸入。  
  
```  
'BeginMoveVB  
  
    'To integrate this code  
    'replace the data source and initial catalog values  
    'in the connection string  
  
Public Sub Main()  
    On Error GoTo ErrorHandler  
  
    ' connection and recordset variables  
    Dim rstAuthors As ADODB.Recordset  
    Dim Cnxn As ADODB.Connection  
    Dim strCnxn As String  
    Dim strSQLAuthors As String  
     ' record variables  
    Dim varBookmark As Variant  
    Dim strCommand As String  
    Dim lngMove As Long  
  
    ' Open connection  
    Set Cnxn = New ADODB.Connection  
    strCnxn = "Provider='sqloledb';Data Source='MySqlServer';" & _  
        "Initial Catalog='Pubs';Integrated Security='SSPI';"  
    Cnxn.Open strCnxn  
  
    ' Open recordset from Authors table  
    Set rstAuthors = New ADODB.Recordset  
    rstAuthors.CursorLocation = adUseClient  
    ' Use client cursor to allow use of AbsolutePosition property  
    strSQLAuthors = "SELECT au_id, au_fname, au_lname, city, state FROM Authors ORDER BY au_lname"  
    rstAuthors.Open strSQLAuthors, strCnxn, adOpenStatic, adLockOptimistic, adCmdText  
  
    rstAuthors.MoveFirst  
  
    Do  
        ' Display information about current record and  
        ' ask how many records to move  
  
        strCommand = InputBox( _  
            "Record " & rstAuthors.AbsolutePosition & _  
            " of " & rstAuthors.RecordCount & vbCr & _  
            "Author: " & rstAuthors!au_fname & _  
            " " & rstAuthors!au_lname & vbCr & _  
            "Location: " & rstAuthors!city & _  
            ", " & rstAuthors!State & vbCr & vbCr & _  
            "Enter number of records to Move " & _  
            "(positive or negative).")  
  
          ' this is for exiting the loop  
        'lngMove = CLng(strCommand)  
  
        lngMove = CLng(Val(strCommand))  
        If lngMove = 0 Then  
            MsgBox "You either entered a non-number or canceled the input box. Exit the application."  
            Exit Do  
        End If  
  
        ' Store bookmark in case the Move goes too far  
        ' forward or backward  
        varBookmark = rstAuthors.Bookmark  
  
        ' Move method requires parameter of data type Long  
        rstAuthors.Move lngMove  
  
        ' Trap for BOF or EOF  
        If rstAuthors.BOF Then  
            MsgBox "Too far backward! Returning to current record."  
            rstAuthors.Bookmark = varBookmark  
        End If  
        If rstAuthors.EOF Then  
            MsgBox "Too far forward!  Returning to current record."  
            rstAuthors.Bookmark = varBookmark  
        End If  
    Loop  
  
    ' clean up  
    rstAuthors.Close  
    Cnxn.Close  
    Set rstAuthors = Nothing  
    Set Cnxn = Nothing  
    Exit Sub  
  
ErrorHandler:  
    ' clean up  
    If Not rstAuthors Is Nothing Then  
        If rstAuthors.State = adStateOpen Then rstAuthors.Close  
    End If  
    Set rstAuthors = Nothing  
  
    If Not Cnxn Is Nothing Then  
        If Cnxn.State = adStateOpen Then Cnxn.Close  
    End If  
    Set Cnxn = Nothing  
  
    If Err <> 0 Then  
        MsgBox Err.Source & "-->" & Err.Description, , "Error"  
    End If  
End Sub  
'EndMoveVB  
```  
  
## <a name="see-also"></a>另請參閱  
 [Move 方法 (ADO)](../../../ado/reference/ado-api/move-method-ado.md)   
 [Recordset 物件 (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)
