# Feedback

! Can't demo in-person
Answer: "log_drive" and "playback_drive" modes

-- log_drive (computer must be connected)
  -- when data queue receives data, flags for logger to print {timestamp, pid, response, current_action} to serial
  -- laptop captures serial data, pipes to log.txt file
  -- not a bottleneck cus data packets are small and data bandwidth from OBD2 is small; 4 pings per second is enough
  -- script also makes a log_drive.h file, which is just a struct array of log packets. 
    -- this will be #include'd in the playback .ino file

-- playback_drive:
  -- data queue is now not fed by real OBD2 request/responses, but instead by the log_drive.h struct array with timestamps
  -- everything downstream runs as if live system were running; thus FULL functionality of the system remains working
  
-- during class demo, I would:
  -- show dashcam/phone video of the real drive side-by-side with playback



