PyPgCurses is intended to be a tool to help explore databases and write queries.

# First Draft UI

    +------------------+----------------+----------+----------+----------+----------+ 
    |  TABLE NAME      |                |          |          |          |          | 
    | field_name_1     | bigserial   P  +--------------------------------------------+
    | field_name_2     | text        U  |          |          |          |          | 
    | field_name_3     | timestamptz IN |          |          |          |          | 
    | field_name_4     | timestamptz IN |          |          |          |          | 
    | field_name_5     | geometry(li I  |          |          |          |          | 
    |                  |                |          |          |          |          | 
    |                  |                |          |          |          |          | 
    |                  |                |          |          |          |          | 
    |                  |                |          |          |          |          | 
    |                  |                |          |          |          |          | 
    |                  |                |          |          |          |          | 
    |                  |                |          |          |          |          | 
    |                  |                |          |          |          |          | 
    |                  |                |          |          |          |          | 
    +------------------+----------------+          |          |          |          | 
    | 1. field_name_1            PBtree |          |          |          |          | 
    | 2. field_name_2            UBtree |          |          |          |          | 
    | 3. field_name_3            IGin   |          |          |          |          | 
    |    field_name_4                   +----------+----------+----------+----------+ 
    | 4. field_name_5            IGiST  |Rows: 1 000             Ex Time: 1 000.4ms | 
    +-------------------------------------------------------------------------------+ 
    |SELECT field_name_1, field_name_2                                              | 
    |FROM TABLENAME                                                                 | 
    |WHERE field_name_2 = 'testing!'                                                | 
    |                                                                               | 
    |                                                                               | 
    |                                                                               | 
    |: command line                                                                 | 
    +-------------------------------------------------------------------------------+ 

# Commands

I'm a VIMer and as such like the concept of having a command line to controll the program.

Arrow Keys would be used to move between the 3 panes in command mode.

    :st :show tables - Shows the list of tables in all schemas in the table window above.
    :cd :cursordoc - Shows help for the key-word under the cursor. (I would like to import pg, postgis, and pgrouting docs) (Results would appear in the query results window.)
    :e :explain - Shows the explain for the query
    :ea :explain analyse - Shows the explain analyse for the query
