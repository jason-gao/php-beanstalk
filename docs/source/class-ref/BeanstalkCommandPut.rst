Beanstalk\\Command\\Put Class Ref
=================================

.. php:namespace:: Beanstalk\Command

.. php:class:: Put

    :Extends: :php:class:`Beanstalk\\Command`
    :Description: The "put" command is for any process that wants to insert a job into the queue
    :Author: Joshua Dechant <jdechant@shapeup.com>


.. topic:: Class Methods

    * :php:meth:`Put::__construct` -- Constructor
    * :php:meth:`Put::getCommand` -- Get the command to send to the beanstalkd server
    * :php:meth:`Put::getData` -- Get the data to send to the beanstalkd server with the command
    * :php:meth:`Put::parseResponse` -- Parse the response for success or failure.

.. php:method:: __construct( $message [ , $priority = 65536 , $delay = 0 , $ttr = 120 ] )

    :Description: Constructor
    :param mixed $message: Message to put in the beanstalkd queue
    :param integer $priority: Job priority.
    :param integer $delay: Number of seconds to wait before putting the job in the ready queue.
    :param integer $ttr: Time to run. The number of seconds to allow a worker to run this job.

.. php:method:: getCommand(  )

    :Description: Get the command to send to the beanstalkd server
    :returns: *string*

.. php:method:: getData(  )

    :Description: Get the data to send to the beanstalkd server with the command
    :returns: *string*

.. php:method:: parseResponse( $response [ , $data = null , $conn = null ] )

    :Description: Parse the response for success or failure.
    :param string $response: Response line, i.e, first line in response
    :param string $data: Data recieved with reponse, if any, else null
    :param Beanstalk\Connection $conn: \Beanstalk\Connection use to send the command
    :returns: *integer* Id of the inserted job
    :throws: *\Beanstalk\Exception* When the server runs out of memory
    :throws: *\Beanstalk\Exception* When the job body is malformed
    :throws: *\Beanstalk\Exception* When the job body is larger than max-job-size in the server
    :throws: *\Beanstalk\Exception* When any other error occurs


