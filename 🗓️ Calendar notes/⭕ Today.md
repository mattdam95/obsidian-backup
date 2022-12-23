_Tareas del día_
- [x] Hablar por pasajes para la fiesta
- [x] Hablar con pablo por turno para el banco
- [x] Averiguar como hicieron los de Ayi el año pasado para la fiesta
- [x] Ver como instalar corredera telescopica
- [x] Médico
- [x] Zapas?
- [x] Ver reserva de salon para el co-working
- [x] Ver reu con pablo, mati y maxi
- [x] Avisar por el proyecto de sellos y preparar el fork
- [x] Cortar pelo?
- [x] Ver el error del select-form
- [x] Hacer documento para mom
- [x] Ver si el sticky del header se puede hacer desde el componente y avisar a Pau
- [x] Base-app 12 a 13
- [ ] 


@import 'node_modules/kolektor-bootstrap/dist/scss/global.scss';

  

.kui-simple-stepper {

    // TODO: Modify this variables with global variables from kb.

    --in-progress: #1c7cd5;

    --pending: #b8b8b8;

    --completed: #219653;

  

    // Component variables:

    --simple-stepper-line-height: 2px;

    --simple-stepper-line-color: var(--pending);

    --simple-stepper-cursor: pointer;

    --simple-stepper-info-margin: 0;

    --simple-stepper-active-font-weight: 400;

    --simple-stepper-icon-color: #fff;

    --simple-stepper-icon-outline: none;

    --simple-stepper-icon-bg-color: var(--simple-stepper-main-color);

  

    --simple-stepper-display-step: initial;

    --simple-stepper-display-info: initial;

    --simple-stepper-display-element: initial;

    --simple-stepper-display-progress-bar: none;

  

    // Component states:

    &--in-progress {

        --simple-stepper-main-color: var(--in-progress);

        --simple-stepper-icon-bg-color: var(--in-progress);

    }

    &--pending {

        --simple-stepper-icon-bg-color: #fff;

        --simple-stepper-main-color: var(--pending);

        --simple-stepper-icon-color: var(--pending);

        --simple-stepper-cursor: not-allowed;

        --simple-stepper-icon-outline: 2px solid var(--pending);

    }

    &--completed {

        --simple-stepper-icon-bg-color: var(--completed);

        --simple-stepper-main-color: var(--completed);

        --simple-stepper-line-color: var(--completed);

    }

  

    .active {

        --simple-stepper-active-font-weight: 500;

    }

  

    // mobile variables settings:

    @media (max-width: 767px) {

        --simple-stepper-display-info: flex;

        --simple-stepper-display-step: none;

        --simple-stepper-display-element: none;

        --simple-stepper-display-progress-bar: block;

        .active {

            --simple-stepper-display-step: initial;

            --simple-stepper-info-margin: 0.5rem;

        }

    }

}

  

@mixin simple-stepper-icon {

    cursor: var(--simple-stepper-cursor);

    margin-right: var(--simple-stepper-info-margin);

    width: 32px;

    height: 32px;

    color: var(--simple-stepper-icon-color);

    box-sizing: content-box;

    transition: 0.3s;

    background-color: var(--simple-stepper-icon-bg-color);

    outline: var(--simple-stepper-icon-outline);

    outline-offset: -2px;

    @extend .rounded-circle;

    @extend .d-flex;

    @extend .justify-content-center;

    @extend .align-items-center;

  

    &:before {

        content: '';

        width: 48px;

        height: 48px;

        @extend .bg-white;

        @extend .position-absolute;

        @extend .rounded-circle;

        z-index: -4;

    }

}

  

.kui-simple-stepper {

    &__step {

        display: inline-block;

    }

  

    &__icon {

        @include simple-stepper-icon();

        font-size: 16px;

        &:after {

            display: var(--simple-stepper-display-element);

            content: '';

            @extend .w-100;

            height: var(--simple-stepper-line-height);

            @extend .position-absolute;

            background-color: var(--simple-stepper-line-color);

            top: 15px;

            left: 15px;

            z-index: -5;

        }

    }

  

    &__info {

        display: var(--simple-stepper-display-info);

        align-items: center;

    }

  

    &__step-number {

        font-size: 0.75rem;

        color: #5c5c5c;

        @extend .font-weight-regular;

        text-transform: uppercase;

    }

  

    &__title {

        @extend .my-1;

        font-weight: var(--simple-stepper-active-font-weight);

    }

  

    &__status {

        display: var(--simple-stepper-display-element);

        color: var(--simple-stepper-main-color);

        font-size: 0.75rem;

        font-weight: 500;

    }

  

    &__row {

        display: block;

        @extend .d-md-flex;

    }

    &__col {

        display: var(--simple-stepper-display-step);

        width: auto;

        z-index: 1;

        &:last-child {

            max-width: fit-content;

            .kui-simple-stepper__icon::after {

                content: none;

            }

            --simple-stepper-line-height: 0;

        }

    }

  

    &__progress-bar {

        display: var(--simple-stepper-display-progress-bar);

        margin-top: 9px;

        height: 3px;

        background-color: #c4c4c4;

        @extend .w-100;

        @extend .rounded-pill;

        @extend .overflow-hidden;

        @extend .position-relative;

    }

  

    &__progress-status {

        @extend .h-100;

        @extend .position-absolute;

        left: 0;

        background-color: var(--in-progress);

    }

}

  

@media (min-width: 767px) {

    .column{

     flex-basis: 0!important;

     flex-grow: 1!important;

     position: relative!important;

    width: 100%!important;

    padding-right: 15px!important;

    padding-left: 15px!important;

    }

 }
