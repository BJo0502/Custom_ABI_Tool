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

