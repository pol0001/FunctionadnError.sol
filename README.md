// SPDX-License-Identifier: MIT
pragma solidity ^0.8.24;

contract Errors {
    uint public DefaultValue;
    uint _currentassert;
    uint _currentrequired;
    uint _currentrevert;

    function GetAssert(uint _initialassert) public{
        _currentassert = _initialassert;
    }

    function GetRequired(uint _initialrequired) public{
        _currentrequired = _initialrequired;
    }

    function GetRevert(uint _initialrevert) public{
        _currentrevert = _initialrevert;
    }
}

contract Derived is Errors{
    constructor(uint ValueForCondition)payable{
        DefaultValue = ValueForCondition;
    }

    function ShowAssertError() public view{
            assert(_currentassert != DefaultValue);
    }

    function ShowRequiredError() public view{
            require(_currentrequired != DefaultValue, "This is a Require error!");
    }

    function ShowRevertError() public view{
            if(_currentrevert == DefaultValue){
                revert("This is a Revert error!");
            }
    }
}
