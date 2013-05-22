datetime
========

This is a simple ABAP class that is a port of PHP's datetime class for easy formatting of date/time strings


It is not complete at this time but the format (initially the most useful method for me) is 'mostly complete'

It will enable you to do something like this:

<pre>
REPORT  z_hello_datetime.
 
  DATA:
        dt type REF TO zcl_datetime
      , fs type string
      , ts type timestamp
      .
 
  GET TIME STAMP FIELD ts.
 
  CREATE OBJECT dt
    EXPORTING timezone = sy-zonlo
              timestamp = ts.
 
  fs = dt->format( 'd M Y H:m' ).
  WRITE: / fs.  "22 May 2013 17:05 
</pre>