# Storage-Slot-Packing
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

contract GasOptimizedPacking {
    // All variables packed into 1-2 storage slots for lower gas on Base
    uint128 public balance;      // 16 bytes
    uint128 public lastReward;   // 16 bytes
    uint64 public lastUpdated;   // 8 bytes
    uint8 public status;         // 1 byte
    bool public isActive;        // 1 byte

    function updateBalance(uint128 newBalance) public {
        balance = newBalance;
        lastUpdated = uint64(block.timestamp);
    }
}
