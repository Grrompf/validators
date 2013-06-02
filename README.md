New Validators for Doctrine and Passwords 
====

Commonly needed validation of password complexity, preventing common passwords against a list and
lookup of a database record by using doctrine. These three validators for ZF2 can easily be configured
as the standard validators by using the option parameter. 
All validators are tested by unit tests. 

Example 
----
 
'validators' => array(
    array('name' => 'User\Form\Validator\PasswordComplexity',
          'options' => array (
              'length'   => '8',
              'treshold' => '80',
          )
    ),
    array('name' => 'User\Form\Validator\CommonPassword',
          'options' => array (  
               'commons'  => array('password', '123456',)
         )       
    ),
    array('name'     => 'User\Form\Validator\DBNoRecordExist',	
          'options' => array( 
               'entity'    => 'Authentication\Entity\Credential',
               'property'  => 'email',
               'adapter'  => $this->getEntityManager(),
          )
    )
)


Requirements
----

* PHP >= 5.3.3
* Zend Framework 2, beta4 or later
* Doctrine2 ORM (for DBNoRecordExist)




License
----

Copyright (c) 2013, Dr. Holger Maerz
All rights reserved.

Redistribution and use in source and binary forms, with or without modification,
are permitted provided that the following conditions are met:

* Redistributions of source code must retain the above copyright notice, this
  list of conditions and the following disclaimer.

* Redistributions in binary form must reproduce the above copyright notice, this
  list of conditions and the following disclaimer in the documentation and/or
  other materials provided with the distribution.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND
ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED
WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE FOR
ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES
(INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES;
LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON
ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
(INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS
SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
