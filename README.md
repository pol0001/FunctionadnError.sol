// SPDX-License-Identifier: MIT
pragma solidity ^0.8.25;

contract DeviceShop {

    function PCprice(uint PC) public pure {
        require(PC <= 20000, "This laptop is 20,000 pesos.");
        require(PC >= 20000, "This laptop is 20,000 pesos, this is your change.");
    }

    function Phoneprice(uint PHONE) public pure {
        if (PHONE <= 15000) {
            revert("This phone is 15,000 pesos.");
        }
        if (PHONE >= 15000) {
            revert("This phone is 15,000 pesos only, this is your change.");
        }
    }

    function iPadprice(uint iPad) public pure {
        require(iPad == 25000, "The iPad price must be exactly 25,000 pesos.");
    }
}
