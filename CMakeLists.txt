cmake_minimum_required (VERSION 2.8)

project(tomsfastmath)

###########################################
#		Include directories
###########################################

include_directories(src/headers)

###########################################
#		Source files & libs
###########################################

set(${PROJECT_NAME}_SRC_FILES
    src/bin/fp_toradix.c
    src/mont/fp_montgomery_calc_normalization.c
    src/numtheory/fp_isprime.c
    src/bin/fp_toradix_n.c
    src/mont/fp_montgomery_reduce.c 
    src/numtheory/fp_isprime_ex.c
    src/bin/fp_unsigned_bin_size.c  
    src/mont/fp_montgomery_setup.c  
    src/numtheory/fp_lcm.c
    src/bit/fp_cnt_lsb.c
    src/mul/fp_mul.c
    src/numtheory/fp_prime_miller_rabin.c
    src/bit/fp_count_bits.c
    src/mul/fp_mul_2.c
    src/numtheory/fp_prime_random_ex.c
    src/bit/fp_div_2.c
    src/mul/fp_mul_2d.c
    src/sqr/fp_sqr.c
    src/addsub/fp_add.c
    src/bit/fp_div_2d.c
    src/mul/fp_mul_comba.c
    src/sqr/fp_sqr_comba.c
    src/addsub/fp_add_d.c
    src/bit/fp_lshd.c
    src/mul/fp_mul_comba_12.c
    src/sqr/fp_sqr_comba_12.c
    src/addsub/fp_addmod.c
    src/bit/fp_mod_2d.c
    src/mul/fp_mul_comba_17.c
    src/sqr/fp_sqr_comba_17.c
    src/addsub/fp_cmp.c
    src/bit/fp_rshd.c
    src/mul/fp_mul_comba_20.c
    src/sqr/fp_sqr_comba_20.c
    src/addsub/fp_cmp_d.c
    src/divide/fp_div.c
    src/mul/fp_mul_comba_24.c
    src/sqr/fp_sqr_comba_24.c
    src/addsub/fp_cmp_mag.c
    src/divide/fp_div_d.c
    src/mul/fp_mul_comba_28.c
    src/sqr/fp_sqr_comba_28.c
    src/addsub/fp_sub.c
    src/divide/fp_mod.c
    src/mul/fp_mul_comba_3.c
    src/sqr/fp_sqr_comba_3.c
    src/addsub/fp_sub_d.c
    src/divide/fp_mod_d.c
    src/mul/fp_mul_comba_32.c
    src/sqr/fp_sqr_comba_32.c
    src/addsub/fp_submod.c
    src/exptmod/fp_2expt.c
    src/mul/fp_mul_comba_4.c
    src/sqr/fp_sqr_comba_4.c
    src/addsub/s_fp_add.c
    src/exptmod/fp_exptmod.c
    src/mul/fp_mul_comba_48.c
    src/sqr/fp_sqr_comba_48.c
    src/addsub/s_fp_sub.c
    src/mul/fp_mul_comba_6.c
    src/sqr/fp_sqr_comba_6.c
    src/bin/fp_radix_size.c
    src/mul/fp_mul_comba_64.c
    src/sqr/fp_sqr_comba_64.c
    src/bin/fp_read_radix.c
    src/mul/fp_mul_comba_7.c
    src/sqr/fp_sqr_comba_7.c
    src/bin/fp_read_signed_bin.c    
    src/mul/fp_mul_comba_8.c
    src/sqr/fp_sqr_comba_8.c
    src/bin/fp_read_unsigned_bin.c  
    src/mul/fp_mul_comba_9.c
    src/sqr/fp_sqr_comba_9.c
    src/bin/fp_reverse.c
    src/mul/fp_mul_comba_small_set.c
    src/sqr/fp_sqr_comba_generic.c
    src/bin/fp_s_rmap.c
    src/mul/fp_mul_d.c
    src/sqr/fp_sqr_comba_small_set.c
    src/bin/fp_signed_bin_size.c    
    src/misc/fp_ident.c
    src/mul/fp_mulmod.c
    src/sqr/fp_sqrmod.c
    src/bin/fp_to_signed_bin.c      
    src/misc/fp_rand.c
    src/numtheory/fp_gcd.c
    src/bin/fp_to_unsigned_bin.c    
    src/misc/fp_set.c
    src/numtheory/fp_invmod.c
)

set(${PROJECT_NAME}_HEADER_FILES
    src/headers/tfm.h
    src/headers/tfm_private.h
)
add_library(${PROJECT_NAME} STATIC ${${PROJECT_NAME}_SRC_FILES} ${${PROJECT_NAME}_HEADER_FILES})
target_compile_definitions(${PROJECT_NAME} PRIVATE -DTFM_NO_ASM -DTFM_TIMING_RESISTANT
)
