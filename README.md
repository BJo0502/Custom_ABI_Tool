# Excel Notes

### Issue: Occasionally, empty rows of data will wind up in the data tables. We need a way to delete any rows that are empty

### Proposed Solution: 
```
Sub DeleteERows()

    Sheets("Sheet1").Select
    
    Range("a2:A15000").Select
    
    Selection.SpecialCells(xlCellTypeBlanks).EntireRow.Delete
    
End Sub
```
### Source: https://stackoverflow.com/questions/9379673/excel-vba-delete-empty-rows

### Issue
How add new values to existing arrays

### Proposed Solution:
```
Private Sub updateArray_Click()

If TextBox1.Value <> vbNullString Then

ReDim Preserve varData(UBound(varData) + 1)

varData(UBound(varData)) = TextBox1.Value

End If

ComboBox1.AddItem TextBox1.Value

TextBox1.Value = vbNullString

End Sub
```

### Source: https://www.ozgrid.com/forum/index.php?thread/103189-edit-array-from-a-userform/
