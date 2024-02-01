- `{ <filed : <name> }` - search exact name in the field
- `{ <field>: { $regex: /<reg>/, $options: 'i' } }` - search requests with regex The $options: 'i' part makes the search case-insensitive
- `{ <field>: {$not: {$lte: 1}}}`  $not = ! not   ,  lte - less then or equal to 
- `{
    "$and": [
    { "Status": { "$regex": "Com" } },
    { "source": { "$regex": "Gl" } }
  ]
}`
- `use your_database_name` - to use your choosen DB
- `show collections` - to list your collections
- `db.my_collection.deleteMany({ Status: { $ne: "Compiled&Executed" } })` - how to delete from my db
