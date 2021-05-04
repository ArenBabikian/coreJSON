# Copyright Amazon.com, Inc. or its affiliates. All Rights Reserved.
# SPDX-License-Identifier: Apache-2.0

HARNESS_FILE=skipObjectScalars_harness
PROOF_UID=skipObjectScalars

# This value was experimentally chosen to provide 100% coverage
# without tripping unwinding assertions and without exhausting memory.

# this comes from the skipCollection proof
CBMC_MAX_BUFSIZE=8

CHECK_FUNCTION_CONTRACTS += skipObjectScalars
USE_FUNCTION_CONTRACTS += skipString
USE_FUNCTION_CONTRACTS += skipAnyLiteral
USE_FUNCTION_CONTRACTS += skipNumber
USE_FUNCTION_CONTRACTS += skipSpace
USE_FUNCTION_CONTRACTS += skipSpaceAndComma

DEFINES += -DJSON_MAX_DEPTH="( $(CBMC_MAX_BUFSIZE) - 2 )"

# UNWINDSET += skipAnyLiteral.0:$(CBMC_MAX_BUFSIZE)
# UNWINDSET += skipLiteral.0:$(CBMC_MAX_BUFSIZE)
UNWINDSET += __CPROVER_contracts_original_skipObjectScalars.0:$(CBMC_MAX_BUFSIZE)

include ../Makefile-json.common

# Substitution command to pass to sed for patching core_json.c. The
# characters " and # must be escaped with backslash.
CORE_JSON_SED_EXPR = s/^static //
