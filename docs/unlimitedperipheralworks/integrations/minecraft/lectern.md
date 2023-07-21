# Lectern

!!! picture inline end
    ![Lectern](lectern.png)


Some librarian often founds lectern pretty useful, but it was always a problem to write long books. Now you can do it with one little program!
<br class="clearBoth" />
<br class="clearBoth" />
<br class="clearBoth" />
<br class="clearBoth" />

## Peripheral methods

| Function                                | Returns | Description                                                                                                                           |
|-----------------------------------------|---------|---------------------------------------------------------------------------------------------------------------------------------------|
| hasBook()                               | boolean | If lectern has book, return true, else false                                                                                          |
| getPageCount()                          | number  | Returns page count, error if no book on lectern                                                                                       |
| getActivePage()                         | number  | Returns active page for book on lectern, error if no book on lectern                                                                  |
| setActivePage(page: number)             | nil     | Tries to set new active page for lectern. Error if no book or page number not between 1 and pageCount                                 |
| getText()                               | table   | Returns a list of strings with text in book                                                                                           |
| isBookEditable()                        | boolean | Returns true if book can be edited via this API                                                                                       |
| addPage(text?: string)                  | boolean | Tries to add new page with text if passed (or empty text). Error if no book or book is not editable                                   |
| removePage(page: number)                | boolean | Tries to remove existed page. Error if no book or book is not editable or page number is not correct                                  |
| editPage(page: number, text: string)    | boolean | Tries to change page text. Error if no book or book is not editable or page number is not correct                                     |
| ejectBook(to: string)                   | [Result](introduction.md#result)  | Tries to move book on lectern to target storage                                                                                       |
| injectBook(from: string, itemQuery?: [ItemQuery](introduction.md#itemquery)) | [Result](introduction.md#result)  | Tries to move book to lectern from target storage. Will transfer first suitable book. If itemQuery provided, book will be filtered by it |

!!! warning
    ItemQuery scope will be limited to written or writable book in any case

## Events

For any computer connected to lectern, you will receive a set of events

### lectern_page_changed

When someone changed page on lectern

#### Values

1. `current_page: number` current page for lectern

### lectern_book_removed

When book removed from lectern

### lectern_book_changed

When book on lectern was placed or replaced with another book

#### Values

1. `book_name: string` name of new book, can be "Book and Quill" or something more useful
2. `player_name?: string` optional name of player who changed the book