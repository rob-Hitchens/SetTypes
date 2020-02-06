# SetTypes
Enumerable Set Types, Ethereum, Solidity

Elaboration and optimization of the Solidity CRUD pattern at: https://github.com/rob-Hitchens/UnorderedKeySet

Four implementations:

- AddressSet
- Bytes32Set
- StringSet
- UintSet

## Usage

```
import "./AddressSet.sol";

contract MyContract {

  using AddressSet for AddressSet.Set;
  AddressSet.Set myAddressSet;
  ...
```

### Uses storage pointers to pass Sets to the library. 

```
myAddressSet.insert(newAddress);
myAddressSet.remove(oldAddress);
uint count = myAddressSet.count();
address key = myAddressSet.keyAtIndex(row);
```

### Works with structs:

```
struct User {
  AddressSet.Set followerSet;
  AddressSet.Set followingSet;
 }
```
### Works with mappings:
```
mapping(bytes32 => AddressSet.Set) productOwnerSets;
```

See SetTypeExamples.sol for example usage. 

