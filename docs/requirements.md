# Business Requirements - Funds Transfer

## BR-001 - Successful Funds Transfer
System shall transfer funds between two valid accounts when sufficient balance exists.

## BR-002 - Balance Validation
System shall validate that the source account has sufficient funds before processing the transfer.

## BR-003 - Invalid Account Rejection
System shall reject transfers when the destination account does not exist or is invalid.

## BR-004 - Duplicate Transaction Prevention
System shall prevent the same transaction (identical transaction ID) from being processed more than once (idempotency).

## BR-005 - Transaction Consistency
System shall maintain data consistency between Transaction Service (X) and Account Service (Y). In case of failure, balances must not be left in an inconsistent state.

## BR-006 - Failed Transaction Logging
System shall log all failed transactions with reason codes for audit purposes.

## BR-007 - Balance Integrity
System shall never allow an account balance to become negative as a result of concurrent or failed transfers.

## BR-008 - Unique Transaction Identifier
System shall generate or accept a unique transaction identifier for every transfer request.
