# XPath

* XML Path Language

utilizing freeformatter.com, I researched XPath.

under validators, there will be xpath validator

You will enter in your XML file, then focus on the xpath input.

lets say I use bookstore.xml
I would put in the root element /bookstore/book/title

This would return every book title under the root element

putting /bookstore/book/title would return all of the book titles ideally


putting /bookstore/book[1] would return the first book element and all of its nested elements such as author, title, etc

putting /bookstore/book[last()] would return the last book sibling under bookstore


# XQuery

very similar to SQL

* FOR
* LET
* WHERE
* ORDER
* RESULT


utilizing xpathtester.com/xquery

youll enter in your XML file  then in the XQuery portion:
    * to return all authors use this
        for $i in /bookstore/book/author
        return $i

    This will return all of the authors names

    In SQL to return all in a certain table it would look like this:

    SELECT * IN [AUTHORS]

    * to return just the text of the elements:

        distinct-values (
            for $i in /bookstore/book
            return $i/price
        )


    * to sort values of elements:

    for $i in /bookstore/book
    let $x := $i/price
    order by $x
    return $x

    *** this would give the values in ascending order
    *** introduces interm variable which helps with readability and reduce complexity

    * to filter through, you would add in the where clause after the let statement in the xquery 
     
    for $i in /CarDB/Car
    let $x := $i/Model
    where $i/Manufacturer = 'BMW'
    order by $x
    return $x


# super helpful guide: https://www.youtube.com/watch?v=NUTvFwXGN-M