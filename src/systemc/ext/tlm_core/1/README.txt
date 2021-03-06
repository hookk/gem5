TLM-1.0 header files
====================

Dir: include/tlm_core/1/

SubDirs: analysis/
	 req_rsp/

Files: README.txt


Comments
========

User code should only #include the tlm or tlm.h header file in the include/
directory and avoid including any of the include files in this directory
directly.  All objects defined in this file hierarchy are in the tlm namespace.

The header files are organizated, by subdirectory, as follows:


tlm_analysis/ 
--------------

This contains the analysis interfaces, ports, and fifos. These files were not
part of the original TLM-1.0 release, but have been grouped with TLM-1.0 in this
release of TLM-2.0

Files:
  analysis.h            (includes the other header files in this directory )
  analysis_fifo.h       (defines tlm_analysis_fifo )
  analysis_if.h         (defines tlm_analysis_if and tlm_delayed_analysis_if )
  analysis_port.h       (defines tlm_analysis_port )
  analysis_triple.h     (defines tlm_analysis_triple )
  write_if.h            (defines tlm_write_if and tlm_delayed_write_if )


req_rsp/
------------

This provides support for TLM modeling based on a request/response pair that 
are passed by value. This is the original TLM 1.0 standard, with the addition 
of an overloading of the blocking transport method with pass-by-reference arguments.

Files:
  req_rsp.h  (includes the key header files from the other directories)

  interfaces/
      core_ifs.h              (defines the TLM 1.0 core interfaces:
					tlm_transport_if
					tlm_blocking_get_if
					tlm_blocking_put_if
					tlm_nonblocking_get_if
					tlm_nonblocking_put_if
					tlm_get_if 
					tlm_put_if 
					tlm_blocking_peek_if
					tlm_nonblocking_peek_if
					tlm_peek_if 
					tlm_blocking_get_peek_if 
					tlm_nonblocking_get_peek_if 
					tlm_get_peek_if              )     
      fifo_ifs.h             ( defines the TLM1.0 fifo interfaces:
					tlm_fifo_debug_if			
					tlm_fifo_put_if
					tlm_fifo_get_if
					tlm_fifo_config_size_if )
      master_slave_ifs.h     ( defines the TLM1.0 master slave interfaces:
					tlm_blocking_master_if
					tlm_blocking_slave_if
					tlm_nonblocking_master_if
					tlm_nonblocking_slave_if 
					tlm_master_if 
					tlm_slave_if )
      tag.h                  ( defines tlm_tag )

  ports/
      nonblocking_port.h     (defines tlm_nonblocking_put_port, 
                                      tlm_nonblocking_get_port and
				      tlm_nonblocking_peek_port )
      event_finder.h         (defines tlm_event_finder_t )

  channels/
      fifo/
          fifo.h             (defines tlm_fifo, includes the other files )
          fifo_peek.h        (defines peek and poke interfaces for tlm_fifo )
          fifo_put_get.h     (defines put and get interfaces for tlm_fifo )
          fifo_resize.h      (defines expand, reduce, bound and unbound
	                      interfaces for tlm_fifo )
          circular_buffer.h  (defines circular buffer used by tlm_fifo )
      req_rsp_channels/
          req_rsp_channels.h     (defines tlm_req_rsp_channel and
	  			          tlm_transport_channel )
          put_get_imp.h          (contains implementatins used by the channels)

  adapters/
  	adapters.h      (defines transport_to_master and tlm_slave_to_transport)
