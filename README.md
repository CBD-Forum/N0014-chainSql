## Overview

The source code is based on [Rippled](https://github.com/ripple/rippled), you need to merge these source code files with Rippled source code files if you want to compile it.

# Details of ChainSQL

By setting the sync_tables, sync_db and auto_sync, you will restore the real DB tables you wanted from blck chain. You can set the DB type arbitrarily, includeing mysql, sqlLite, oracle and so on.

Defined two new transaction types for the DB operation ,named sqlStatement and tableListSet. sqlStatement is used to insert  ,update or delete records, tableListSet is used to create a table and other operations to the table-self.

You can operate the DB or send DB operations to the block chain by using the RPC API functions, supplied by the RPC modules.

The table module send data request to other nodes and sort the tx datas from other nodes, then give the right transaction data to the  misc modules. This module also seeks every ledger in local block chain to get the compatible table data to send back to the required nodes.

The misc module analysis transaction data to get the real sql, then operator the DB ussing these real sql sentences;

Further more ,storage modules make you check the DB before sending tx data to the block chain ,this makes it possible if we can operate DB timely.

See [http://www.chainsql.net](http://www.chainsql.net)

## License

ChainSQL is under the GNU General Public License v3.0. See the [LICENSE](./LICENSE) directory for details.
