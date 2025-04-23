##  Vimeo API - Initiate Video Trim Operation

This repository provides a brief overview of using the Vimeo API to trim videos.  Note that this operation creates a derivative version of the video and does not result in a completely new, independent video asset in your library.

The following illustrates a trim operation on a Vimeo video:

![image](https://github.com/user-attachments/assets/6bb574fc-1d73-457d-a90b-760f7c720735)


~~~```bash
curl -X POST \
  -H "Authorization: Bearer {YOUR_VIMEO_TOKEN}" \
  -H "Content-Type: application/json" \
  -d '{
    "trim_start": "10",
    "trim_end": "25"
  }' \
  "[https://api.vimeo.com/videos/](https://api.vimeo.com/videos/){YOUR_VIDEO_ID}/trim"
~~~

Response:

A successful trim initiation returns a JSON response like this:

~~~```JSON
{
  "status": "OK",
  "trim_status": "IN_PROGRESS",
  "trim_job_id": 2368497,
  "progress": 0
}
~~~

Breakdown:

`"status": "OK"`: Indicates the request was successful.

`"trim_status": "IN_PROGRESS"`: Shows that the trimming operation is currently being processed.

`"trim_job_id": 2368497`: A unique ID for the trim job, which could potentially be used to check the status (though the method below is noted as deprecated).

`"progress": 0`: The current progress of the trimming operation (0% in this case).

Results:

![image](https://github.com/user-attachments/assets/f900ed59-3e20-4af2-8128-23b29f4c3208)
A Vimeo entry derivative version history.
