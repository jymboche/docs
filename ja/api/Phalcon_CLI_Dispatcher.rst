Class **Phalcon\\CLI\\Dispatcher**
==================================

*extends* abstract class :doc:`Phalcon\\Dispatcher <Phalcon_Dispatcher>`

*implements* :doc:`Phalcon\\Events\\EventsAwareInterface <Phalcon_Events_EventsAwareInterface>`, :doc:`Phalcon\\DI\\InjectionAwareInterface <Phalcon_DI_InjectionAwareInterface>`, :doc:`Phalcon\\DispatcherInterface <Phalcon_DispatcherInterface>`

Dispatching is the process of taking the command-line arguments, extracting the module name, task name, action name, and optional parameters contained in it, and then instantiating a task and calling an action on it.  

.. code-block:: php

    <?php

    $di = new Phalcon\DI();
    
    $dispatcher = new Phalcon\CLI\Dispatcher();
    
      $dispatcher->setDI($di);
    
    $dispatcher->setTaskName('posts');
    $dispatcher->setActionName('index');
    $dispatcher->setParams(array());
    
    $handle = $dispatcher->dispatch();



Constants
---------

*integer* **EXCEPTION_NO_DI**

*integer* **EXCEPTION_CYCLIC_ROUTING**

*integer* **EXCEPTION_HANDLER_NOT_FOUND**

*integer* **EXCEPTION_INVALID_HANDLER**

*integer* **EXCEPTION_INVALID_PARAMS**

*integer* **EXCEPTION_ACTION_NOT_FOUND**

Methods
-------

public  **setTaskSuffix** (*string* $taskSuffix)

Sets the default task suffix



public  **setDefaultTask** (*string* $taskName)

Sets the default task name



public  **setTaskName** (*string* $taskName)

Sets the task name to be dispatched



public *string*  **getTaskName** ()

Gets last dispatched task name



protected  **_throwDispatchException** ()

Throws an internal exception



protected  **_handleException** ()

Handles a user exception



public *string*  **getTaskClass** ()

Possible task class name that will be located to dispatch the request



public :doc:`Phalcon\\CLI\\Task <Phalcon_CLI_Task>`  **getLastTask** ()

Returns the lastest dispatched controller



public :doc:`Phalcon\\CLI\\Task <Phalcon_CLI_Task>`  **getActiveTask** ()

Returns the active task in the dispatcher



public  **__construct** () inherited from Phalcon\\Dispatcher

Phalcon\\Dispatcher constructor



public  **setDI** (:doc:`Phalcon\\DiInterface <Phalcon_DiInterface>` $dependencyInjector) inherited from Phalcon\\Dispatcher

Sets the dependency injector



public :doc:`Phalcon\\DiInterface <Phalcon_DiInterface>`  **getDI** () inherited from Phalcon\\Dispatcher

Returns the internal dependency injector



public  **setEventsManager** (:doc:`Phalcon\\Events\\ManagerInterface <Phalcon_Events_ManagerInterface>` $eventsManager) inherited from Phalcon\\Dispatcher

Sets the events manager



public :doc:`Phalcon\\Events\\ManagerInterface <Phalcon_Events_ManagerInterface>`  **getEventsManager** () inherited from Phalcon\\Dispatcher

Returns the internal event manager



public  **setActionSuffix** (*string* $actionSuffix) inherited from Phalcon\\Dispatcher

Sets the default action suffix



public  **setModuleName** (*string* $moduleName) inherited from Phalcon\\Dispatcher

Sets the module where the controller is (only informative)



public *string*  **getModuleName** () inherited from Phalcon\\Dispatcher

Gets the module where the controller class is



public  **setNamespaceName** (*string* $namespaceName) inherited from Phalcon\\Dispatcher

Sets the namespace where the controller class is



public *string*  **getNamespaceName** () inherited from Phalcon\\Dispatcher

Gets a namespace to be prepended to the current handler name



public  **setDefaultNamespace** (*string* $namespace) inherited from Phalcon\\Dispatcher

Sets the default namespace



public *string*  **getDefaultNamespace** () inherited from Phalcon\\Dispatcher

Returns the default namespace



public  **setDefaultAction** (*string* $actionName) inherited from Phalcon\\Dispatcher

Sets the default action name



public  **setActionName** (*string* $actionName) inherited from Phalcon\\Dispatcher

Sets the action name to be dispatched



public *string*  **getActionName** () inherited from Phalcon\\Dispatcher

Gets the lastest dispatched action name



public  **setParams** (*array* $params) inherited from Phalcon\\Dispatcher

Sets action params to be dispatched



public *array*  **getParams** () inherited from Phalcon\\Dispatcher

Gets action params



public  **setParam** (*mixed* $param, *mixed* $value) inherited from Phalcon\\Dispatcher

Set a param by its name or numeric index



public *mixed*  **getParam** (*mixed* $param, [*string|array* $filters], [*mixed* $defaultValue]) inherited from Phalcon\\Dispatcher

Gets a param by its name or numeric index



public *string*  **getActiveMethod** () inherited from Phalcon\\Dispatcher

Returns the current method to be/executed in the dispatcher



public *boolean*  **isFinished** () inherited from Phalcon\\Dispatcher

Checks if the dispatch loop is finished or has more pendent controllers/tasks to disptach



public  **setReturnedValue** (*mixed* $value) inherited from Phalcon\\Dispatcher

Sets the latest returned value by an action manually



public *mixed*  **getReturnedValue** () inherited from Phalcon\\Dispatcher

Returns value returned by the lastest dispatched action



public *object*  **dispatch** () inherited from Phalcon\\Dispatcher

Dispatches a handle action taking into account the routing parameters



public  **forward** (*array* $forward) inherited from Phalcon\\Dispatcher

Forwards the execution flow to another controller/action Dispatchers are unique per module. Forwarding between modules is not allowed 

.. code-block:: php

    <?php

      $this->dispatcher->forward(array('controller' => 'posts', 'action' => 'index'));




public *boolean*  **wasForwarded** () inherited from Phalcon\\Dispatcher

Check if the current executed action was forwarded by another one



public *string*  **getHandlerClass** () inherited from Phalcon\\Dispatcher

Possible class name that will be located to dispatch the request



